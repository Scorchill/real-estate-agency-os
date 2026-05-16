# Team FAQ — TEMPLATE

> **Diana, seed this at setup — then let it grow.** This is the home for the operational knowledge that currently lives in your head and across scattered docs. Pull the pertinent material out of those Google Docs — company policy, process, "how we do things" — and refactor it into reference entries here, so the team can consult it directly instead of asking you. It answers the questions a team member would otherwise Slack you at 11pm: which document goes where, what's our policy on X, when to check with you first. Seed it with a handful; add to it whenever a question comes up twice. Two ways to build it — (1) fill in the entries below by hand, or (2) paste the interview prompt at the bottom into a chat and let it draft the FAQ from your answers. The example entries below are illustrative — replace them with your team's real questions and answers.

## How the system uses this file

Any specialist may consult this file. The orchestrator (`00`) checks it when a team member asks a general "how do we..." question rather than asking for deal work — it answers from here, or points to the system file or specialist that holds the answer. An entry can be a direct answer, or a pointer ("that lives in `_shared/trec_reference.md`"). Both are useful — half the value is just knowing *where to look*.

## What does NOT go here

No client names, deal details, or PII — same discipline as the voice profiles. Deal-specific status belongs in that deal's own conversation, not here. This file is standing operational knowledge only.

---

## Documents & filing

**Q: A deal just went under contract — where does the executed contract go, and what starts getting tracked?**
A: Hand the deal to `04_transaction_coordinator` — it builds the Deal Jacket (key dates, document checklist, who-owes-what) and derives TREC deadlines from `_shared/trec_reference.md`. *[Diana: add where the team files the executed contract itself — shared drive, transaction-management tool, etc.]*

**Q: How does a teammate pick up one of my deals if I'm out?**
A: Every deal has a case file at `_shared/cases/<case_id>.md`. Hand the teammate the case_id; they read the file and have the full state — Lead Card, Property Brief, Comms log, Deal Jacket, handoff trail. No reconstruction needed.

## Process & policy

**Q: A lead came in for a ZIP that's not in our usual territory — what do I do?**
A: Check `_shared/austin_market_brief.md` ("Outside this territory"). The orchestrator marks the owning-agent assignment "(provisional)" and flags Diana to confirm before showings begin. *[Diana: add any standing rule — e.g., a referral threshold.]*

**Q: What's our standard option period, and who do we use for inspections?**
A: *[Diana: fill in standing vendor preferences and any default terms the team uses.]*

## When to check with Diana

**Q: How do I know if something needs Diana's sign-off?**
A: Check your own section in `_shared/team_roster_TEMPLATE.md` — the **Elevates to Diana** list. If it's there, ask before acting. If it's under **Handles independently**, you're clear.

## Tools & access

**Q: What tools does the team use (MLS, CRM, email), and how does a new hire get access?**
A: *[Diana: list the team's core tools and who sets up access for a new hire.]*

---

## Don't want to seed this by hand?

Paste the prompt below into any chat in the project. It will interview you and produce a finished FAQ in this format — you just save the result.

```
I'm seeding the team FAQ for our system. Interview me to build it.

Ask me a few questions at a time, conversationally — don't dump the whole list at once.

I'm looking for the operational questions my team asks me over and over — the
"which document goes where," "what's our policy on X," "who do we use for Y,"
"where do I find Z" questions. For each one:
- What's the question, in the words a team member would actually ask it?
- What's the answer? (It's fine for the answer to be a pointer — "that's in
  trec_reference.md" or "ask 04" — half the value is knowing where to look.)

Also ask me which tools the team uses and how a new hire gets access, where we
log deals, and any standing policies (option periods, vendor preferences,
territory rules).

When you have enough, produce a complete FAQ in the exact format of
`_shared/team_faq_TEMPLATE.md` — light category headers, each entry a Q and an
A, no placeholder entries left. Then write it to `_shared/team_faq_TEMPLATE.md`
in this folder — or, if I'd rather place it myself, give it to me in a code block.

No client names, deal details, or PII — standing operational knowledge only.
```
