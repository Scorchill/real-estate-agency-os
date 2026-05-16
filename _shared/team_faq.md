# Team FAQ

> **Pre-seeded with 8 starter Q&As covering common boutique-RE operational questions.** This is the home for the operational knowledge that currently lives in your head and across scattered docs — pull the pertinent material here so the team can consult it directly instead of asking you. It answers the questions a team member would otherwise Slack you at 11pm. Diana edits, adds, or removes entries to fit the team's real practices. Three Q&As below have *[Diana: ...]* placeholders (four spots total — contract-filing location, option-period & vendors, and tools/access provisioner) — they need Diana's team-specific answer; the rest are reasonable boutique-RE defaults. Two ways to extend: (1) edit entries below by hand, or (2) paste the interview prompt at the bottom of this file into a chat and let it draft new entries from your answers. Grow this file whenever a question comes up twice. To start from a blank slate instead of editing here, use `_shared/team_faq_TEMPLATE.md`. **No client names or deal details — standing operational knowledge only.**

## How the system uses this file

Any specialist may consult this file. The orchestrator (`00`) checks it when a team member asks a general "how do we..." question rather than asking for deal work — it answers from here, or points to the system file or specialist that holds the answer. An entry can be a direct answer, or a pointer ("that lives in `_shared/trec_reference.md`"). Both are useful — half the value is just knowing *where to look*.

## What does NOT go here

No client names, deal details, or PII — same discipline as the voice profiles. Deal-specific status belongs in that deal's own conversation, not here. This file is standing operational knowledge only.

---

## Documents & filing

**Q: A deal just went under contract — where does the executed contract go, and what starts getting tracked?**
A: Hand the deal to `04_transaction_coordinator`. It opens (or updates) the case file's Deal Jacket section in `_shared/cases/<case_id>.md` — key dates, document checklist, who-owes-what. TREC deadlines come from the executed contract; `_shared/trec_reference.md` teaches you what to look for in the paragraph numbers. *[Diana: confirm where the team files the executed contract itself — shared drive, transaction-management tool, etc.]*

**Q: How does a teammate pick up one of my deals if I'm out?**
A: Every deal has a case file at `_shared/cases/<case_id>.md`. Hand the teammate the case_id; they read the file and have the full state — Lead Card, Property Brief, Comms log, Deal Jacket, handoff trail. No reconstruction needed.

## Process & policy

**Q: A lead came in for a ZIP that's not in our usual territory — what do I do?**
A: Check `_shared/austin_market_brief.md` ("Outside this territory") for the team's primary ZIPs. 00 will mark the owning-agent assignment "(provisional)" per `_shared/team_roster.md` and flag Diana to confirm before showings begin. For a deal genuinely outside scope, a referral handoff out is usually the right move.

**Q: What's our standard option period, and who do we use for inspections?**
A: *[Diana: fill in standing vendor preferences and any default terms the team uses. The Texas TREC contract doesn't set a default option period — it's negotiated per deal. The team's typical preference goes here.]*

## When to check with Diana

**Q: How do I know if something needs Diana's sign-off?**
A: Check your own section in `_shared/team_roster.md` — the **Elevates to Diana** list. If it's there, ask before acting. If it's under **Handles independently**, you're clear. When in doubt, ask — Diana would rather get the heads-up.

**Q: A buyer wants to make an aggressive counter — when do I loop Diana in?**
A: Counter-offer strategy on any deal > $750K elevates to Diana per the roster. For deals under that threshold, the owning agent runs the counter; if the situation feels unusual (multi-offer, atypical contingencies, large concessions), elevate regardless.

## Tools & access

**Q: What tools does the team use (MLS, CRM, email), and how does a new hire get access?**
A: Unlock MLS (Austin), Gmail / Google Workspace, *[Diana: add the team's CRM-lite or transaction-management tool here]*. New-hire access setup: *[Diana: list who provisions accounts.]*

**Q: I want to run the system on my own machine — how do I get set up?**
A: Open Claude Code, choose **Use an existing folder**, point it at the team's shared workspace folder. Leave the Instructions field blank — the root `CLAUDE.md` primes Claude automatically. See README §3 (Onboarding) for the full first-day walkthrough.

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
A, no placeholder entries left. Then write it to `_shared/team_faq.md`
in this folder — or, if I'd rather place it myself, give it to me in a code block.

No client names, deal details, or PII — standing operational knowledge only.
```
