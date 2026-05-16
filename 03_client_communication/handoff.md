# 03_client_communication — Handoff

## What I accept

- `02 → 03` for a first-conversation email after research
- `04 → 03` for a situational comms draft during a live deal (inspection-issue, financing-delay, missed-deadline, competing-offer, other) — now with `Severity` field (not `Tone`)
- `01 → 03` for a qualification follow-up draft to a thin lead
- Chat header from 00 for a one-off draft request

## What I produce

- **Visible deliverable:** the draft, in a markdown blockquote or fenced block, copy-pasteable. The human reviews, edits, sends.
- **Case-file representation:** appended Comms log entry + trail entry. Stage update per the rules.
- **Possible outgoing handoffs:**
  - `03 → 04` when a deal moves under contract (post-acceptance setup)
  - No outgoing for one-off drafts, qualification follow-ups (awaiting lead reply), or routine in-deal comms

## Severity vocabulary (from 04)

Closed values: `routine | heads-up | urgent | escalate`. Sets tone and follow-up cadence, NOT strategic position.

## 03 → 04 (deal moves under contract) body format

```
**Offer details:**
- Buyer / Seller / Property / Accepted price / Concessions

**Key dates** (verify against executed contract):
- Effective date / Option period / Earnest money / Financing contingency / Closing

**Open threads:**
- <thread 1>
```

Per `HANDOFF_PROTOCOL.md`; appended to the case file's Deal Jacket section starter.

## 01 → 03 (qualification follow-up) — incoming body format

```
**Gap list:** <fields the lead needs to answer>
**Relationship context:** <how the agent knows them, prior touches>
**Tone cues:** <from prior touches, if any>
```

03 produces a warm, non-pushy draft asking for the missing info. Output is typically email or text in the agent's voice.

## Worked examples

See `examples.md`.
