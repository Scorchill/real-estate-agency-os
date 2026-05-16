# Diana's Real Estate Agency OS — A Multi-Folder ICM System for a 4-Person Real Estate Team

An **AI back office** for your real estate team, running inside Claude Code. Every deal becomes a **case file** the system opens, fills, and tracks across its full lifecycle.

- **You paste:** a lead, a comp question, a deal update.
- **The orchestrator routes** to the right specialist (or answers directly for caseload questions).
- **The work lands in the case file** — intake, comps, drafts, deal jacket — and stays there across sessions and teammates.
- **Ask the system anything across deals:** *"what's the status of the Rodriguez deal?"* · *"show me Tom's caseload."* The case files are the answer.

## What this system helps with

Every capability below either **adds to a case file** or **reads across them**.

**Work that fills the case file** (one section per specialist):

- **Qualifying new leads** → Lead Card. Captures intent, budget, timeline, location, constraints into a clean section of the case file. (`01_lead_qualifier`)
- **Structuring property research** → Property Brief. Synthesizes the Austin market context into a ready-to-run comp worksheet instead of a blank page; appends to the case file. (`02_property_research`)
- **Drafting client communication** → Comms log entry. Emails, texts, follow-ups in the owning agent's voice; includes the four canonical situations (missed showings, competing offers, inspection issues, financing delays). (`03_client_communication`)
- **Coordinating live deals** → Deal Jacket. Once under contract: deadlines, document checklists, who-owes-what, risk flags — all maintained inside the case file. (`04_transaction_coordinator`)

**Work that reads across case files:**

- **Routing every request** — every paste enters `00_orchestrator`, which decides which specialist handles it (or answers directly if it's a caseload question or onboarding).
- **Asking about the caseload** — at any time, ask *"show me Tom's active deals,"* *"what's the status of the Rodriguez deal,"* *"which deals have option periods this week,"* *"give me today's briefing."* The system reads `_shared/cases/` directly and answers. (`00_orchestrator`)

**What it doesn't do:** showings, presenting offers, negotiating, attending closing — those stay with the humans. The system preps; the agent acts. (`TASK_MAP.md` has the full in-scope / human-only breakdown.)

---

## How it works

Think of it as a small office with one filing cabinet. The front desk (`00_orchestrator`) reads every request, pulls the relevant **case file** if one applies, and either routes the work to the right specialist (01–04) — who reads the file, does their part, and **files their work back in** — or answers directly when it's a caseload question.

A few things worth knowing:

- **One case file per deal.** A new lead opens a **case file** at `_shared/cases/<case_id>.md` — just paste the intake info and the orchestrator hands it to 01, which mints the case_id and starts the file. Any chat can pick that deal back up by referring to the case_id — same file gets updated whether you opened it Monday or Friday, in your chat or Tom's.
- **You paste, the system routes.** Drop a request into chat — a raw lead, a comp question, an inspection result, an "update on Todd" reply. The orchestrator reads it, pulls the relevant **case file** if one applies, and routes. You don't have to know which folder you need.
- **The chat is the interface; the case file is the record.** Specialists show you their work in chat (drafts, summaries, recommended angles) and at the same time **append the structured content** (Lead Card, Property Brief, Comms log entry, Deal Jacket section) to the case file. Chat is conversational; the file is the persistent record that survives across sessions and across teammates.
- **Hand a deal to a teammate by sharing the case_id.** Tom picks up Sarah's deal — she tells him `2026-05-14-petrov`, he mentions it in his chat, the orchestrator reads the file, he's caught up on everything that's happened.
- **Ask about the caseload anytime.** Cross-deal questions don't route to a specialist — the orchestrator reads `_shared/cases/` directly. *"Show me everything Tom has under contract"* is a filesystem read, not a database you maintain.
- **Operational questions too.** Which document goes where, when something needs Diana's sign-off — the system answers from `_shared/team_faq.md` instead of that question sitting in Diana's inbox.
- **The system pauses naturally for review.** When a specialist finishes its part, the chat ends on a clear next-step note (*"Handing to Property Research — should land next turn"* or *"Bob: edit, then send when ready"*). Nothing client-facing leaves your hands without you reviewing it.

The system *preps* and *files*; the human agent *acts*. It never sends an email, presents an offer, or attends a closing.

---

## Where this system fits

This system is the team's **prep layer**. It slots into how the team already works; it doesn't replace it.

- **Before the system:** leads arrive through the team's existing funnel — calls, emails, referrals, portal inquiries — and an agent picks up the prospect. The system doesn't catch leads or decide who owns them.
- **Inside the system:** the agent opens a case file by pasting intake (or updates an existing one). The orchestrator routes the work; the specialists qualify, research, draft, and coordinate, in that agent's voice.
- **After the system:** the agent does the human parts — showings, presenting offers, negotiating, closing — and sends what the system drafted.

A few things sit deliberately outside it: lead routing and notifications, balancing deal load across agents, and the assignment decision itself (humans pick who owns each new deal; the system records it in the case file header). Those stay in the team's existing tools, or are candidates for separate tooling later. Naming that boundary is the point — the system does the repeatable knowledge work well precisely because it doesn't pretend to be the whole business.

The team runs it as a **shared workspace Diana maintains** as the source of truth — the case files at `_shared/cases/` are the team's persistent record across sessions and teammates.

---

## 1. Architecture

Five specialist folders, one orchestrator, one persistent case file per deal. The orchestrator routes (and answers caseload queries directly). Specialists hand work to each other by appending to the case file at `_shared/cases/<case_id>.md`. The chat is the interface; the filesystem is the database.

**Deal flow:**

```
                 ┌─────────────────────────────┐
   user paste ──→│  00_orchestrator            │──→ caseload answers
                 │  (router + caseload view)   │
                 └──────────────┬──────────────┘
                                │
        ┌──────────┬────────────┼────────────┬──────────┐
        ▼          ▼            ▼            ▼          ▼
     ┌────┐     ┌────┐       ┌────┐       ┌────┐    boundary:
     │ 01 │────▶│ 02 │──────▶│ 03 │──────▶│ 04 │    Diana / human
     └────┘  ◀──└────┘       └────┘ ◀────▶└────┘    (prep only)
              re-qualify              comms loop

   one-offs: 00 → any specialist directly
   onboarding: 00 → _onboarding/
```

**Persistence layer:**

```
                  _shared/cases/<case_id>.md          ← one file per deal
                  ├─ header (stage, status, owner)
                  ├─ Lead Card       (written by 01)
                  ├─ Property Brief  (written by 02)
                  ├─ Comms log       (written by 03)
                  ├─ Deal Jacket     (written by 04)
                  └─ Handoff trail   (every specialist appends)
                          ▲
                          │ read + append every turn
                          │
              all five specialists ─┴─ 00 (for caseload)
```

The five specialists each have four files: `identity.md` (who they are), `rules.md` (how they operate), `examples.md` (worked scenarios), `handoff.md` (their case-file body format, referencing the root `HANDOFF_PROTOCOL.md`).

---

## 2. Typical request walkthrough

**Happy path — full lifecycle:**

1. Bob captures Alfred Gardener at an open house and pastes the details. 00 routes (`**Lead Qualifier — Alfred Gardener (Bob)**`).
2. 01 prompts for missing fields, mints the case_id, appends the **Lead Card** to `_shared/cases/2026-05-13-gardener.md` → stage `qualified`.
3. 02 produces a **Property Brief** (comp worksheet + neighborhood notes + recommended angle) and appends it → stage `researched`.
4. 03 reads `voice_bob.md` and drafts a first-conversation email in Bob's voice. Bob sends.
5. Offer accepted. 03 hands to 04. 04 builds the **Deal Jacket** inside the case file and tracks to close → stage `under-contract` → `closed`.

**Caseload query:**
Diana asks *"summarize Tom's active deals."* 00 reads `_shared/cases/`, filters by owning_agent=Tom and status=active, returns a brief summary. No routing to a specialist.

**Onboarding:**
A new hire types *"I'm new."* 00 walks them through `_onboarding/start.md` → voice capture → practice run. The practice case file lands in `_shared/cases/_practice/` and stays out of the real caseload.

**Scope boundary:**
A counter-offer situation lands on Diana's desk. 00 names the boundary (`**Scope boundary — Rodriguez counter (Diana)**`), routes prep work to 02 (comps) and 03 (buyer-side draft), explicitly names Diana as the human owner of the actual conversation.

---

## 3. Onboarding a new team member

Three steps:

1. **Read this README** (~10 minutes).
2. **Type "I'm new" in chat** or open `_onboarding/start.md` directly.
3. **Walk through the three onboarding steps** — orientation, voice capture, practice run (~30 minutes total).

Total time to operational: ~45 minutes — well inside the "operational in a day" bar. The practice run uses your captured voice to draft a real-feeling client email; the practice case file at `_shared/cases/_practice/` stays out of the real caseload.

---

## 4. Setup — Diana's first run

Pre-seeded files keep setup short.

1. **Get the repo from GitHub onto your computer.** Clone or download.
2. **Open Claude Code**, choose **Use an existing folder**, point at the repo, leave Instructions blank — the root `CLAUDE.md` primes Claude automatically.
3. **Open `_shared/team_roster.md`** — edit names, tenure, elevation rules to match your team (replace illustrative Tom/Sarah/Bob with your actual team).
4. **Edit the three `[Diana: ...]` entries in `_shared/team_faq.md`** — contract-filing location, option-period & vendors, and tools/access (four placeholder spots across three Q&As). The other 5 Q&As are reasonable defaults; edit them as needed.
5. **Build your voice profile** via the interview prompt in `_shared/voice/voice_TEMPLATE.md` — Diana's pre-seeded illustrative profile is already there as a worked example.
6. **Have each team member type *"I'm new"* in chat** (or open `_onboarding/start.md` directly) when they log in.

Total time for Diana: ~30–45 minutes.

---

## 5. Maintenance — keeping it current

Reference for ongoing updates. Most maintenance is editing one file.

- **New hire** → add their entry to `_shared/team_roster.md`; have them run `_onboarding/start.md`.
- **Voice shift** → ask Claude to update `_shared/voice/voice_<agent>.md` (or re-run the interview).
- **Standard changes** (elevation rules, who handles what) → edit `_shared/team_roster.md`.
- **New recurring operational question** → append to `_shared/team_faq.md`.
- **Quarterly** → refresh prices and market-condition language in `_shared/austin_market_brief.md`.
- **When TREC changes a form** → update `_shared/trec_reference.md` paragraph references.

Changes take effect immediately. No restart, no migration. The case files keep moving.

---

## 6. Design decisions and tradeoffs

**Case file as the spine.** Every deal becomes `_shared/cases/<case_id>.md`. Specialists read at turn start, append on handoff. The chat is the interface; the file is the source of truth. Survives context compression. Lets one teammate hand a deal to another by just sharing the case_id. Caseload queries are filesystem reads.

**Single handoff envelope.** `HANDOFF_PROTOCOL.md` defines one schema all five specialists use. Chat shows a one-line bold header; the structured content lives in the case file.

**`team_roster.md` + `team_faq.md` for team knowledge.** Together they address the brief's pain: *"newest agent Slacks me at 11pm asking which document needs to go where."* The FAQ answers operational questions (documents, process, vendors); the roster answers elevation questions (when to involve Diana). Both pre-seeded so the system is useful day one — Diana edits, doesn't author from scratch.

**Per-agent voice profiles with labeled-neutral-draft fallback.** The brief specifies *"voice of the agent on the deal."* If a profile is missing, 03 produces a labeled neutral draft (not a fake voice) and the agent humanizes before sending. All four current agents ship with illustrative voice profiles to eliminate day-one halts; the interview prompt in `voice_TEMPLATE.md` is the real product for capturing real voices.

**Severity in 04 → 03.** The procedural urgency of a situation is closed-vocabulary (`routine | heads-up | urgent | escalate`) — distinct from the strategic position the agent owns. Keeps the agent-vs-system line crisp.

**Three tradeoffs:**

- *Config lives in plain files the team owns.* `team_roster.md`, `team_faq.md`, voice profiles — all markdown the team reviews. Every change is deliberate and visible.
- *The system tracks each deal's owning agent (in the case file header) and lets you query across deals — but it doesn't assign new leads or load-balance.* Who's up next for a referral, who's overloaded, who answers an inbound first — those stay in the team's existing tools.
- *Labeled neutral draft, not halt, when a voice file is missing.* Faster day-one usability; agents capture their voice via `_onboarding/voice_capture.md` when they're ready.

---

## 7. Folder map

- **`00_orchestrator/`** — the router + caseload view. Reads every request, picks a specialist OR answers caseload queries from `_shared/cases/` directly. Walks new hires through onboarding.
- **`01_lead_qualifier/`** — first-contact intake. Mints case_id, appends Lead Card to the case file. Hands off to 02 (research), 03 (qualification follow-up if lead-side gaps exist), or holds at stage `new` if more info is needed.
- **`02_property_research/`** — synthesizes `_shared/austin_market_brief.md` into neighborhood context + comp worksheet. Appends Property Brief to the case file. Can route back to 01 if research surfaces a buyer/location mismatch.
- **`03_client_communication/`** — drafts client-facing copy in the owning agent's voice. Appends Comms log entries. Receives `01 → 03` (qualification follow-up) and `04 → 03` (situational comms with Severity).
- **`04_transaction_coordinator/`** — owns the deal once under contract. Maintains the Deal Jacket inside the case file. Flags risks; hands to 03 with Severity for comms. Emits `04 → close` when the deal closes.
- **`_shared/`** — `cases/` (one file per deal + `_practice/` for onboarding runs), `team_roster.md` + `team_roster_TEMPLATE.md`, `team_faq.md` + `team_faq_TEMPLATE.md`, `austin_market_brief.md`, `trec_reference.md`, `when_offline.md`, `voice/` (Diana/Tom/Sarah/Bob illustrative profiles + `voice_TEMPLATE.md` for new hires).
- **`_onboarding/`** — three-step new-hire flow (start, voice_capture, practice_request).
- **`_intake/`** — `buyer_TEMPLATE.md` and `seller_TEMPLATE.md` — canonical field-set references 01 uses.
- **`HANDOFF_PROTOCOL.md`** — single envelope schema, lifecycle, status vocabulary, case_id format, special transitions. All specialists reference this.
- **`TASK_MAP.md`** — O*NET 41-9022 decomposition showing which tasks are in-scope and which are human-only. Optional reading; design rationale.

---

## A note on what's assumed

Diana's brief named her but not her three other agents, their specialties, or her processes. Where the brief left gaps, the system fills them with plausible defaults — each one flagged inline in the file where it appears:

- **Team member names** (Tom, Sarah, Bob) and their current tilts.
- **Pre-seeded FAQ entries** — three Q&As marked `[Diana: ...]` for her to verify (four placeholder spots total); the other five are reasonable boutique-RE defaults.
- **Illustrative voice profiles** for all four agents (Diana included) — flagged at the top of each voice file as a demo, not a real captured voice.
- **Seed example case file** (Alfred Gardener) — a worked example, not a real deal.
- **Austin neighborhood specifics** — pulled from real Austin geography but illustrative.
- **TREC** (Texas Real Estate Commission) **reference details** — verify against current trec.texas.gov before relying on specific phrasing.

Everything else traces to the brief or to O*NET 41-9022 (`TASK_MAP.md`).
