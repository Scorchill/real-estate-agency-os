# 04_transaction_coordinator — Handoff

## What I accept

- `03 → 04` when a deal moves under contract (post-acceptance setup → initial Deal Jacket build)
- Chat header from 00 for a one-off TC question (deadline lookup, document status, etc.)
- The case file at `_shared/cases/<case_id>.md` (read at turn start)

## What I produce

Per `HANDOFF_PROTOCOL.md`:

- **Visible deliverable:** Deal Jacket summary in chat (status, flags, what's next); the full Deal Jacket lives in the case file.
- **Case-file representation:** updated Deal Jacket section + trail entry.
- **Possible outgoing handoffs:**
  - `04 → 03` for situational comms (now with `Severity`)
  - `04 → close` when deal closes

## 04 → 03 (situational comms) body format

```
**Situation:** <inspection-issue | financing-delay | missed-deadline | competing-offer | other>
**Severity:** <routine | heads-up | urgent | escalate>
**Facts:**
- <fact 1, factual, no speculation>
- <fact 2>
**Recipient:** <buyer | seller | both>
```

03 produces the draft; agent reviews and sends.

## 04 → close (deal closes) body format

```
**Closing summary:**
- Final price / closed-on date / which side won (buyer or seller)
- Any post-close items (utility hookups, file archival)

**Optional next:** hand to 03 to draft a thank-you / nurture email if the agent wants one
```

Case-file header updates: stage → `closed`, status → `won` or `lost`.

## Worked examples

See `examples.md`.
