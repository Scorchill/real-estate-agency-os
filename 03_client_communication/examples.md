# 03_client_communication — Examples

Four scenarios: first-conversation email with voice loaded (a), the four canonical situations in Diana's voice (b1–b4), the missing-voice-file case for a hypothetical new hire (c), and a qualification follow-up draft via 01 → 03 (d).

Each scenario opens with the chat header, shows the case-file read at turn start, shows the draft, and notes the Comms log entry appended to the case file.

---

## Scenario (a) — First-conversation email, voice loaded (happy path)

**Setup:** Diana asks 03 to draft the first email to a new buyer, Priya Patel, following a Property Brief from 02. Case file at `_shared/cases/2026-05-14-patel.md` is at stage `researched`. `voice_diana.md` has substantive content.

**Chat header:**

```
**Client Comms — Priya Patel (Diana)**
First-conversation email after research. *Case 2026-05-14-patel*
```

**Case file read at turn start:** `_shared/cases/2026-05-14-patel.md` shows Lead Card (78703, budget $950K, 3BR, close-in, met Diana at Hyde Park open house) and Property Brief (three properties surfaced, 4207 Bull Creek flagged as just back on market). Comms log is empty. Voice resolution: read `_shared/voice/voice_diana.md` — substantive content. Drafting in Diana's voice.

**Draft:**

```
Subject: 78703 — a few things worth looking at

Hey Priya —

Really glad we got to talk Saturday. I pulled a short list for 78703 in the $950K range — three properties that hit your 3BR requirement and stay close-in.

Wanted to flag one at 4207 Bull Creek before the week gets away from us. It just came back on the market after falling out of contract (inspection issue the seller fixed), which means less competition than usual for something this tight to the lake.

Happy to chat through the list whenever works. No rush — just didn't want the Bull Creek one to go quiet without giving you a heads up.

— Diana
```

> Diana: edit anything that doesn't sound right, then send. The Bull Creek flag is a judgment call — pull if you want to lead softer.

**Comms log entry appended to `_shared/cases/2026-05-14-patel.md`:**

```
- 2026-05-14 — first-conversation email, 78703 short list with Bull Creek flag — drafted in Diana's voice; sent: N
```

**Stage update:** `researched → in-comms`. Trail entry: `2026-05-14 02 → 03 · "First-conversation draft for Priya Patel; Bull Creek flagged"`.

---

## Scenario (b) — The four canonical situations (Diana as owning agent)

Each sub-example is a compact worked draft in Diana's voice (`voice_diana.md` is loaded for all four). Structural elements from `rules.md` are noted inline. All four operate on the same case file `_shared/cases/2026-04-20-gardener.md` (different days during the deal) — read at turn start before drafting.

---

### b1 — Missed showing

**Chat header:**

```
**Client Comms — Alfred Gardener (Diana)**
Missed-showing apology and reschedule. *Case 2026-04-20-gardener*
```

**Setup:** Diana's buyer, Alfred Gardener, drove to a showing at 1807 Bouldin Ave that couldn't happen — the listing agent never confirmed and the property was occupied when they arrived. Diana asks 03 to draft an apology and reschedule offer. Case file read: stage `in-comms`, prior comms log entries show two earlier showings went fine.

**Structural elements:** apology without grovel, reschedule offer, brief reason if known.

```
Subject: Today's showing — sorry about that

Hey Alfred —

Really sorry about this afternoon. The listing agent hadn't confirmed the showing time and the property wasn't accessible when you got there — that's on me to have nailed down before you drove out.

I'm going to call them directly to lock in a new time. Can you do Thursday or Friday this week? Let me know what works and I'll confirm it before you leave.

— Diana
```

> Diana: adjust the day offer to your actual calendar, then send.

**Comms log entry appended:**

```
- 2026-04-22 — missed showing at 1807 Bouldin; apology + reschedule offer — drafted in Diana's voice; sent: N
```

---

### b2 — Competing offer

**Chat header:**

```
**Client Comms — Alfred Gardener (Diana)**
Competing-offer heads-up to buyer on 3412 Cesar Chavez. *Case 2026-04-20-gardener*
```

**Setup:** Diana represents Alfred (buyer) on 3412 Cesar Chavez. A second offer just came in while Alfred's offer is on the table. Diana asks 03 to draft a message to Alfred with the facts and his options. Incoming from 04: `Severity: heads-up`.

**Structural elements:** situational facts, no pressure, options the buyer has.

```
Subject: 3412 Cesar Chavez — wanted to give you a heads up

Hey Alfred —

Quick heads up: a second offer came in on the property this afternoon. I wanted you to know before anything moves.

A few things you can do from here: hold where you are and see how the seller responds, strengthen your offer (price, fewer contingencies, faster close), or sit tight if the numbers don't work for you at this point. No pressure either way — just wanted to make sure you had the full picture.

Happy to talk through it if that helps. I can also pull comps again quickly if you want a fresh read before you decide.

— Diana
```

> Diana: confirm the facts are right (number of offers, any seller-set deadline), then send.

**Comms log entry appended:**

```
- 2026-04-24 — competing-offer heads-up on 3412 Cesar Chavez; severity heads-up — drafted in Diana's voice; sent: N
```

---

### b3 — Inspection issue

**Chat header:**

```
**Client Comms — Alfred Gardener (Diana)**
Inspection-issue heads-up on 908 Academy Dr. *Case 2026-04-20-gardener*
```

**Setup:** Alfred's inspection on 908 Academy Dr came back with evidence of past roof leaks around the skylight. Diana asks 03 to draft a heads-up before Alfred hears about it elsewhere. Incoming from 04: `Severity: heads-up`.

**Structural elements:** heads-up framing, severity assessment from facts, next-step proposal.

```
Subject: 908 Academy — inspection note

Hey Alfred —

Wanted to flag something from the inspection before we figure out next steps. The inspector noted evidence of past roof leaks around the skylight — some staining in the attic. He's recommending a roofer take a look to assess whether it's been fixed or is still active.

This kind of flag isn't automatically a dealbreaker; a lot of it depends on what a roofer finds. I'd suggest getting one out this week so we have a real read before the option period closes. From there we can decide whether to renegotiate, ask the seller to address it, or walk if it's worse than it looks.

Happy to call if you want to talk it through. I'll line up the roofer visit and we can decide from there.

— Diana
```

> Diana: confirm the option-period deadline and adjust the roofer recommendation if you want a specific contractor named.

**Comms log entry appended:**

```
- 2026-04-28 — inspection issue on 908 Academy (roof/skylight); severity heads-up — drafted in Diana's voice; sent: N
```

---

### b4 — Financing delay

**Chat header:**

```
**Client Comms — Alfred Gardener (Diana)**
Financing-delay update; lender ETA pushed 5 days. *Case 2026-04-20-gardener*
```

**Setup:** Alfred's lender has flagged that final loan approval will come in 5 days later than the financing contingency date due to a missing document from his employer. Diana asks 03 to draft an update. Incoming from 04: `Severity: urgent` (deadline pressure, but no escalation needed — Diana still owns the call).

**Structural elements:** facts, what's being done, realistic ETA, what it means for the deadline.

```
Subject: Quick update on financing

Hey Alfred —

Wanted to keep you in the loop. The lender flagged that they're waiting on an employment-verification document before they can issue final approval — that pushed the timeline back about 5 days from what we expected.

Your loan officer is working on getting that document from your employer now. Realistic ETA for approval is end of next week. I've given the seller's agent a heads up; we're requesting a short extension on the financing contingency to cover the gap.

Nothing alarming here — just a paperwork delay. I'll keep you posted as soon as the document clears. Let me know if you have questions in the meantime.

— Diana
```

> Diana: confirm the lender's actual ETA and the extension request status before sending.

**Comms log entry appended:**

```
- 2026-05-02 — financing-delay update; lender ETA pushed 5 days; severity urgent — drafted in Diana's voice; sent: N
```

---

## Scenario (c) — Missing voice file (hypothetical new hire Avery)

**Setup:** A hypothetical fifth agent, Avery, recently joined the team but hasn't yet completed `_onboarding/voice_capture.md`. Avery asks 03 to draft a follow-up to her client Kevin after a second showing at 3809 Terry Ave. `voice_avery.md` does not exist.

The default behavior is **labeled neutral draft** — produced, copy-pasteable, with a clear flag at the top. The agent humanizes before sending.

**Chat header:**

```
**Client Comms — Kevin (Avery)**
Second-showing follow-up. *No case_id — one-off draft*
```

**Voice resolution:** Read `_shared/voice/voice_avery.md` — file not found. Producing labeled neutral draft.

**Draft:**

> *(Voice profile for `Avery` not loaded — this is a neutral structural draft. Humanize before sending. To make this drafting work in your voice, complete the voice interview at `_onboarding/voice_capture.md`.)*
>
> ```
> Subject: Following up on Terry Ave
>
> Hi Kevin,
>
> Wanted to check in after the second showing at 3809 Terry Ave yesterday. It seemed like the property landed differently the second time through — curious where your head is at on it.
>
> If anything came up on the walkthrough you'd like to talk through — layout, condition, anything else — happy to jump on a call. The property has been on the market a while, so there's no immediate pressure, but that can shift.
>
> Let me know what's most helpful — a call, a text, or another visit.
>
> Best,
> Avery
> ```

**Comms log entry appended (or, for a one-off with no case, noted in chat only):**

```
- 2026-05-15 — second-showing follow-up for Kevin; LABELED NEUTRAL DRAFT (voice_avery.md missing) — sent: N
```

---

### The halt-with-skeleton path (preserved as an opt-in)

The prior behavior — halting the full draft and surfacing two options to the agent — is preserved as an explicit option the agent can request. Use it when there's a stated reason to halt rather than producing a neutral draft (e.g., the agent wants to fill the voice file first and would rather not work from a neutral skeleton). On request, 03 surfaces:

> *"I don't have <owning_agent>'s voice profile yet. Two options:*
> *(a) Complete the voice interview at `_onboarding/voice_capture.md` (~10 minutes). Then ask me again; I'll draft in your voice.*
> *(b) I produce a structural skeleton now — bullet points and rough phrasing, **no voice styling** — that you humanize before sending. Want the skeleton?"*

This path is no longer the default. The default is the labeled neutral draft above.

---

## Scenario (d) — Qualification follow-up draft (01 → 03)

**Setup:** Tom met Mr. Todd at an open house in Travis Heights. The intake was thin — Todd said "looking in the area" and gave a phone number, nothing else. 01 captured what's known and is handing to 03 to draft a warm, non-pushy follow-up that asks for the missing fields. Case file at `_shared/cases/2026-05-15-todd.md` is at stage `new`, status `active`.

**Incoming handoff from 01 (body):**

```
**Gap list:** specific budget range, pre-approval status and amount, timeline (when wanting to buy), specific neighborhoods of interest, must-haves (bed/bath/yard/parking/etc)
**Relationship context:** Tom met Todd at the Travis Heights open house Saturday 5/10. Only stated interest: "looking in the area." Exchanged phone numbers; no email captured yet.
**Tone cues:** Friendly but reserved at the open house. Not a heavy talker. Comfortable with text.
```

**Chat header:**

```
**Client Comms — Mr. Todd (Tom)**
Qualification follow-up; gap list from 01. *Case 2026-05-15-todd*
```

**Case file read at turn start:** stage `new`, Lead Card present with gaps listed, Comms log empty. Voice resolution: `_shared/voice/voice_tom.md` substantive. Drafting in Tom's voice. Text format requested (Todd preferred text).

**Draft:**

```
Hey Mr. Todd — Tom here from Saturday's open house in Travis Heights. Glad we connected.

Quick one when you have a sec: a few details would help me line up the right places for you to look at.

- Budget range you're working with?
- Are you pre-approved with a lender yet, or still in that stage?
- Any sense of timeline — buying in the next month, the next few?
- Beyond Travis Heights, any other neighborhoods on your list?
- Anything you definitely need (bedrooms, parking, yard, etc) vs. flexible on?

No rush on any of it — whatever you can share, I'll work with. Easier to text or hop on a quick call?

— Tom
```

> Tom: confirm the format (text vs. email) and edit if any of the questions feel too much for a first follow-up. The intent is warm and low-friction.

**Comms log entry appended to `_shared/cases/2026-05-15-todd.md`:**

```
- 2026-05-15 — qualification follow-up text; asking for budget, pre-approval, timeline, neighborhoods, must-haves — drafted in Tom's voice; sent: N — qualification follow-up
```

**Stage update:** stays `new`. Status stays `active`. Trail entry: `2026-05-15 01 → 03 · "Qualification follow-up draft for Todd; awaiting lead reply"`. No outgoing handoff — when Todd replies, the agent pastes the reply, 00 routes back to 01 to resume intake.

---

*Reference:* See `rules.md` for the voice resolution rule, severity vocabulary, lane discipline, and the four canonical situations. See `handoff.md` for incoming/outgoing format details. See `HANDOFF_PROTOCOL.md` at the root for envelope and lifecycle.
