# Team roster — TEMPLATE

> **Diana, fill this in at setup.** This file tells the system who's on your team, who owns what kinds of work, and what each agent should elevate to you instead of handling themselves. You have two ways to do it — (1) edit the sections below by hand, replacing Tom, Sarah, and Bob with your actual team, or (2) use the interview prompt at the bottom of this file, which walks you through it and produces a finished roster. Bob, Tom, and Sarah below are illustrative names. No client names or deal details here.

## Diana (team lead, 8 years)

**Sign-offs required from me on:**
- Counter-offer strategy on any deal > $750K
- Any fee adjustment or commission split change
- First three transactions of any new agent (currently: Bob)
- Inspection situations involving structural findings
- Any client who's worked with the team before (warm referral handling)

**I explicitly delegate:**
- Standard intake on cold leads from open houses
- Routine comp pulls (any agent can run their own)
- TC document chasing once a deal is under contract
- After-hours showings on already-qualified leads

## Tom (5 years, currently buyer-active tilt)

**Owns:**
- Cold inbound to Tom's email or "@tom" on Slack
- Past clients tagged T-* in his book
- Any buyer-side deal in 78745, 78704, 78751 by default unless reassigned

**Elevates to Diana:**
- Fee or commission questions
- Counter-offer strategy on deals > $750K
- Multiple-offer situations on listings the team is repping

**Handles independently:**
- Standard buyer-side intake, qualification, showings, drafting through close
- All routine comp work and market context
- TC coordination for his deals (looping in 04 as needed)

## Sarah (5 years, currently seller-active tilt)

**Owns:**
- Cold inbound to Sarah's email or "@sarah" on Slack
- Past clients tagged S-* in her book
- Listing-side deals by default unless reassigned

**Elevates to Diana:**
- Pricing strategy on listings > $1M
- Pre-listing improvements advice requiring on-site walkthrough (Diana joins)
- Counter-offer strategy on offers received

**Handles independently:**
- Standard listing-side intake, prep, MLS coordination, drafting through close
- Routine comp work and market context
- TC coordination for her listings

## Bob (6 months, ramping)

**Owns:**
- Cold inbound to Bob's email or "@bob" on Slack
- Open-house follow-ups he ran

**Elevates to Diana:**
- Anything > $850K
- Anything outside 78704 / 78745 (Bob is still building neighborhood depth)
- Inspection issues with structural, electrical, or foundation findings
- Multiple-offer situations (any side)
- Counter-offers
- Any client conversation that feels like it's going sideways

**Handles independently:**
- Standard buyer-side intake under $850K in 78704 / 78745
- Routine comp pulls
- Drafting first-conversation emails and routine follow-ups (in his voice — see `voice/voice_bob.md` once filled in)
- Day-of showings on confirmed appointments

---

> **For new hires:** When you join, fill out a section like the ones above with your own Owns / Elevates to Diana / Handles independently. Diana finalizes it.

---

## Owning-agent assignment — clean vs. provisional

When a lead arrives, the orchestrator (00) assigns an owning agent. There are two defined states:

**Clean assignment** — the lead clearly falls within one agent's territory or ownership rules (by inbox, Slack handle, ZIP code, or deal side). That agent is the owning agent. The `owning_agent` field in handoffs is just the name — no caveat. Work proceeds normally.

**Provisional assignment** — the lead spans multiple agents' territories, falls outside every defined territory, or the ownership rule is ambiguous (e.g., one ZIP is in Tom's territory, the adjacent ZIP belongs to no one). In this case:
- The orchestrator picks the best-fit agent based on proximity, availability, or deal type.
- The `owning_agent` field in all handoffs is written as **"<name> (provisional)"** — for example, "Tom (provisional)".
- The orchestrator flags Diana to confirm or reassign before showings begin.
- Work proceeds through intake and research on the provisional assignment; Diana confirms before the deal moves into active showing or offer stages.

"(provisional)" is a defined, consistent value — not an improvisation. If you see it in a handoff, it means the above protocol is in effect and Diana has been flagged.

---

## Don't want to fill this in by hand?

Paste the prompt below into any chat in the project. It will interview you and produce a finished roster in this exact format — you just save the result.

```
I'm setting up the team roster for our system. Interview me to build it.

Ask me a few questions at a time, conversationally — don't dump the whole list at once.

First, the team:
- Who's on the team? For each person, their name, roughly how long they've been
  with me, and any current tilt (more buyer-active, more seller-active, a
  neighborhood they know best).

Then, for each agent (one at a time):
- What kinds of leads or deals do they OWN by default? (by inbox or Slack handle,
  by neighborhood, by referral source, by deal side)
- What should they ELEVATE to me — check with me before acting — instead of
  handling on their own? (price thresholds, deal types, situations, tenure-based
  caution for newer agents)
- What do they HANDLE INDEPENDENTLY, start to finish, without looping me in?

Then, for me (the team lead):
- What am I the final sign-off on, across the whole team?
- What do I explicitly delegate and want off my plate?

When you have enough, produce a complete team roster in the exact format of
`_shared/team_roster_TEMPLATE.md` — one section per person, my own section using
the inverted "Sign-offs required from me on" / "I explicitly delegate" format, the
agents using "Owns" / "Elevates to Diana" / "Handles independently". No placeholder
names left. Then write the finished roster to `_shared/team_roster.md` in this
folder — or, if I'd rather place it myself, give it to me in a code block.

No client names or deal details — roles, rules, and routing only.
```
