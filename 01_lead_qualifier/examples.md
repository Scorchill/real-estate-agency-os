# 01_lead_qualifier — Examples

## Scenario 1: New buyer lead — happy path

**User pastes** (Bob, after Saturday open house):
> Got a Zillow lead, Alfred Gardener, looking for 2BR in 78704, around $700K, wants to be in by end of summer.

**01 responds** (after 00's chat header routes to Lead Qualifier):

```
**Lead Qualifier — Alfred Gardener (Bob)**
New buyer lead from Saturday's open house; opening intake.
```

Minting case_id `2026-05-13-gardener` and creating `_shared/cases/2026-05-13-gardener.md` with header (stage `new`, status `active`, side `buyer`, owning agent Bob).

Got it — Alfred Gardener, captured. Before I hand this to research, four things to nail down:

1. Budget — is the $700K a hard ceiling, or is that a ballpark? Is she pre-approved, and if so, for how much and with which lender?
2. Timeline — "end of summer" usually means close by mid-August to move before a lease ends. What's her actual deadline, and what's driving it?
3. Location flex — 78704 is the primary ask. Is she open to 78745 if 78704 inventory is thin, or is the neighborhood non-negotiable?
4. Constraints — any must-haves beyond 2BR? (Yard, parking, walkability, schools, no HOA, no flips?)

**User replies** (Bob):
> She's pre-approved at $725K, lender is Frost Bank, she said the written letter should arrive by Friday. Lease ends August 31 so needs to close by mid-August. She'll consider 78745 if nothing fits in 78704. Needs a fenced yard for her dog, walkability is a priority, and she said no flips.

**01 responds:**

That closes it — I have everything research needs. Appending the Lead Card to `_shared/cases/2026-05-13-gardener.md`, advancing stage to `qualified`, and handing to 02.

Appended to the case file:

```
## Lead Card  ·  01 · 2026-05-13

- Intent: buying (primary residence)
- Budget: $650K–$725K · pre-approved Frost Bank · written approval expected by Fri
- Timeline: close by 2026-08-15 (lease ends 8/31)
- Location: 78704 primary, 78745 acceptable
- Constraints: 2BR minimum, fenced yard for dog, walkability priority, no flips
- Source: Zillow lead, met at Saturday open house
- Why moving: lease ends, wants ownership before next school year

**Unknowns:**
- Credit score range
- School requirements (no kids mentioned, but unconfirmed)
- HOA tolerance
```

Trail entry appended: `2026-05-13 01 → 02 · "Intake complete; comps for 78704/78745 needed plus school-zone context"`

Then the chat header for 02 fires next turn:

```
**Property Research — Alfred Gardener (Bob)**
Intake just completed; comps and school zones next. *Case 2026-05-13-gardener*
```

---

## Scenario 2: Seller wanting to list

**User pastes** (Sarah):
> Homeowner in 78745 contacted us. She wants to list her house. Said she bought it about 6 years ago and is thinking about upsizing.

**01 responds** (after 00's chat header routes to Lead Qualifier):

```
**Lead Qualifier — Tran seller lead 78745 (Sarah)**
New seller inbound; opening intake.
```

Minting case_id `2026-05-14-tran` and creating `_shared/cases/2026-05-14-tran.md` (stage `new`, status `active`, side `seller`, owning agent Sarah).

Good — seller-side. Four things I need before we can hand this to research for a CMA:

1. Address — what's the property address? Need it for the comp pull.
2. Timeline — is she planning to list this season, or still in the "thinking about it" stage? Does she have a target move date?
3. Price expectation — has she seen any online estimates (Zillow, Redfin)? Does she have a number in mind, or is she coming in blank?
4. Why now — upsizing suggests a life trigger. Kids, space, job change? Helps us read urgency and whether she's a motivated seller or just testing the market.

**User replies** (Sarah):
> Address is 4817 Manchaca Rd 78745. She wants to list this spring, so within the next 60 days. She's seen Zestimates and thinks it's worth around $650K but isn't sure. Upsizing because of a second kid on the way.

**01 responds:**

That's enough to start the seller-side CMA. Appending the Lead Card to `_shared/cases/2026-05-14-tran.md`, advancing stage to `qualified`, and handing to 02 for listing comps in 78745.

Appended to the case file:

```
## Lead Card  ·  01 · 2026-05-14

- Intent: selling (primary residence, owner-occupied ~6 years)
- Budget: target ~$650K (Zestimate-anchored; needs calibration)
- Timeline: list within 60 days (spring; motivated — second child coming)
- Location: 4817 Manchaca Rd, Austin TX 78745
- Constraints: list-first vs buy-first stance unknown
- Source: inbound contact (channel unconfirmed)
- Why moving: upsizing for growing family (second child on the way)

**Unknowns:**
- Interior condition, updates, square footage
- Mortgage payoff / equity position (affects net-proceeds sensitivity)
- Whether she's already shopping for the next home (list-first vs. buy-first)
```

Trail entry appended: `2026-05-14 01 → 02 · "Seller intake complete; listing-side CMA in 78745, calibrate $650K anchor"`

---

## Scenario 3: Incomplete lead — agent gaps, hold

**User pastes** (Sarah):
> Got an email through the team@ inbox. Someone named Mendez said they're "thinking about selling" and want to know what their place is worth. That's all the info we have.

**01 responds** (after 00's chat header routes to Lead Qualifier):

```
**Lead Qualifier — Mendez inbound (Sarah)**
Thin inbound; opening intake, classifying gaps.
```

Minting case_id `2026-05-14-mendez` and creating `_shared/cases/2026-05-14-mendez.md` (stage `new`, status `active`, side `seller` probable, owning agent Sarah).

Not enough to hand to research yet. Here's how the gaps split:

**Agent-side (likely things you know or can dig up):**
- Which inbox the email hit, and whether there's any prior touch in our CRM
- Whether the team@ auto-reply went out and what it said
- Any signature block or address fragment in the original email

**Lead-side (only Mendez can answer):**
- Property address / ZIP
- Timeline — "thinking about selling" covers everything from next month to next year
- Price expectation — have they seen online estimates? Do they have a number in mind?
- Why now — life event, market read, or opportunistic?

Three options:
- **(a)** Answer what you can from your side now; I hold for the lead-side gaps until they reply on their own.
- **(b)** Hand to 03 to draft a warm follow-up email asking the lead-side questions.
- **(c)** Both — you fill in your side, I hand to 03 for the outbound.

**User replies** (Sarah):
> Let me check the CRM and the email signature, I'll get back to you in a bit. Hold for now.

**01 responds:**

Holding. Case file stays at stage `new`, status `active`. When you have the agent-side info, paste it back and we'll pick up.

The Lead Card appended now is partial — `Unknowns` captures the agenda:

```
## Lead Card  ·  01 · 2026-05-14

- Intent: selling (probable; said "thinking about selling")
- Budget: not stated
- Timeline: not stated
- Location: not stated
- Constraints: not stated
- Source: team@ inbox (channel: email)
- Why moving: not stated

**Unknowns:**
- Property address / ZIP (lead-side)
- Timeline — curious vs. actively listing this year (lead-side)
- Price expectation — informed by Zestimate? prior CMA? (lead-side)
- Why now — life event, market read, opportunistic (lead-side)
- CRM history / prior touch (agent-side — Sarah checking)
- Original email signature, any address fragment (agent-side — Sarah checking)
```

No trail entry for an outgoing handoff — none happens. Trail just records the open: `2026-05-14 00 → 01 · "Thin inbound; intake opened, awaiting agent-side info"`.

---

## Scenario 4: Thin lead intake with gap classification → hand to 03

**User pastes** (Tom):
> hey so I have a buyer, mr todd, he wants to look in the area, yadda yadda.

**01 responds** (after 00's chat header routes to Lead Qualifier):

```
**Lead Qualifier — Mr. Todd buyer lead (Tom)**
Thin intake; opening case file and classifying gaps.
```

Minting case_id `2026-05-15-todd` and creating `_shared/cases/2026-05-15-todd.md` (stage `new`, status `active`, side `buyer`, owning agent Tom).

Got it — almost nothing on the wire yet, so let me sort what I'd need into two piles.

**Agent-side (things you probably know about Mr. Todd already):**
- Lead source — where did he come to us? (referral, past client, sign call, open house, online)
- Prior history — have we worked with him before? Any prior CRM record?
- Your contact preference for him — call, text, email, what's worked before
- Your read on relationship temperature — warm intro, cold lead, somewhere in between

**Lead-side (only Mr. Todd can answer):**
- Budget range and pre-approval status (lender named? written or verbal?)
- Timeline — when does he need to be in?
- Specific areas — "the area" is too broad; ZIPs or neighborhoods
- Must-haves and dealbreakers (beds/baths, yard, schools, walkability, no flips, etc.)
- Why moving — what's driving this

Three options for how to close the gap:
- **(a)** You answer the agent-side now; I hold for Mr. Todd to surface lead-side info on his own.
- **(b)** I hand to 03 to draft a warm follow-up email or text to Mr. Todd asking the lead-side questions in your voice.
- **(c)** Both — you fill in your side, I hand to 03 to draft outbound.

**User replies** (Tom):
> b. He's a referral from my client Janet Reyes — closed with her last fall. Never met him, just one phone call from Janet vouching for him. Email's fine.

**01 responds:**

Going with (b). Appending what we know to the Lead Card (mostly Unknowns at this point), then handing to 03 to draft the follow-up. Case stays at stage `new`, status `active` — drafting a qualification follow-up doesn't advance the stage; we're still waiting on Mr. Todd.

Appended to the case file:

```
## Lead Card  ·  01 · 2026-05-15

- Intent: buying (assumed; needs confirmation)
- Budget: not stated
- Timeline: not stated
- Location: "the area" — needs ZIPs/neighborhoods
- Constraints: not stated
- Source: referral from Janet Reyes (Tom's past client, closed fall 2025)
- Why moving: not stated

**Unknowns:**
- Budget range + pre-approval status (lender, written/verbal)
- Timeline
- Specific areas — ZIPs or neighborhoods
- Must-haves and dealbreakers
- Why moving
- Confirmation of intent (assumed buying based on Tom's framing)
```

Trail entry appended: `2026-05-15 01 → 03 · "Qualification follow-up: warm email to Mr. Todd asking lead-side gaps; referral from Janet Reyes"`

Then the chat header for 03 fires next turn:

```
**Client Comms — Mr. Todd qualification follow-up (Tom)**
Warm intro email; gaps to fill listed in handoff. *Case 2026-05-15-todd*
```

The 03 handoff body 01 produces:

> **Relationship context:** referred by Janet Reyes (Tom's past client, closed fall 2025). Tom has not met Mr. Todd; one phone call from Janet vouching. First outbound from Tom directly.
>
> **Tone cue:** warm and unhurried — this is a referral, not a cold lead. Tom wants to honor the Janet relationship without being pushy.
>
> **Gaps to ask about** (don't dump the full list — pick the natural openers):
> - Budget range + whether he's pre-approved
> - Timeline (when he needs to be in)
> - Specific areas he's looking — neighborhoods or ZIPs
> - Must-haves
> - Why moving / what's driving this
>
> **Channel:** email. Voice: Tom (see `_shared/voice/voice_tom.md`).

---

## Scenario 5: Continuing intake from a prior turn

**Context:** A week ago, Tom opened case `2026-05-15-todd` (Scenario 4) and we handed to 03 for a qualification follow-up email. Tom sent it. Mr. Todd has now replied.

**User pastes** (Tom):
> Got a reply from Mr. Todd. Here it is:
> "Hi Tom — thanks for reaching out. Janet's spoken highly of you. Quick intro: I'm relocating from Houston for a job at Tesla in Q3, looking to be in by August. Budget is up to $850K, pre-approved with Wells Fargo (written letter, $875K cap). Mainly looking in Mueller, East Austin (78702/78722), or anywhere walkable to a coffee shop and a park. Need 3BR/2BA minimum, home office, no HOA if avoidable. My wife's not relocating until December so I need a place we can both live in but she doesn't see it first. Let me know what's a good time to call."

**01 responds** (after 00's chat header routes to Lead Qualifier via the update-to-existing-case rule):

```
**Lead Qualifier — Mr. Todd intake continuing (Tom)**
Lead replied; reading the case file, filling the gaps. *Case 2026-05-15-todd*
```

Read `_shared/cases/2026-05-15-todd.md` — prior Lead Card from 2026-05-15 has source (referral from Janet), most other fields as Unknowns. Mr. Todd's reply closes nearly all of them.

Updating the Lead Card and advancing stage to `qualified`. Case file Last update bumped to 2026-05-22 09:14.

Appended to the case file (the prior Lead Card stays; this new section appends):

```
## Lead Card  ·  01 · 2026-05-22 (continued)

- Intent: buying (confirmed — primary residence, relocating)
- Budget: up to $850K · pre-approved Wells Fargo (written, $875K cap)
- Timeline: move in by 2026-08 (Q3 job start at Tesla)
- Location: Mueller, East Austin (78702/78722), or walkable-to-coffee-and-park anywhere
- Constraints: 3BR/2BA minimum, home office, prefer no HOA, must be livable solo until Dec when wife joins (no "fixer that she won't approve sight unseen")
- Source: referral from Janet Reyes (carried from prior Lead Card)
- Why moving: relocating from Houston for Tesla job (Q3 start)

**Unknowns:**
- (none material — minor: school/childcare needs not stated; no kids mentioned)
```

Trail entry appended: `2026-05-22 01 → 02 · "Intake completed on lead's reply; comps for Mueller/78702/78722 under $850K, walkability check"`

Then the chat header for 02 fires next turn:

```
**Property Research — Mr. Todd (Tom)**
Intake just closed; comps and walkability next. *Case 2026-05-15-todd*
```
