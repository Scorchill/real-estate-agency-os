# 01_lead_qualifier — Handoff

## What I accept

- A chat header routing me work from 00 (new lead, continuing intake, or update to an existing case)
- For new leads: the user's raw message or filled intake-template paste — that's the intake material
- For continuing intake: the case file at `_shared/cases/<case_id>.md` (read at turn start)
- For 02 → 01 back-edge (re-qualification): the divergence note from 02; re-engage the agent to clarify

## What I produce

A handoff conforming to `HANDOFF_PROTOCOL.md`:

- **Chat representation:** one-line announcement (per 00's chat header format)
- **Case-file representation:**
  - Appended `Lead Card` section in `_shared/cases/<case_id>.md`
  - Trail entry: `<date> 01 → <next> · "<one-line>"`
  - Stage update in header: `qualified` if complete, stays `new` if not
- **Possible outgoing handoffs:**
  - `01 → 02` when intake is complete → research starts
  - `01 → 03` when lead-side gaps need outbound qualification follow-up → 03 drafts the message
  - No handoff (stage stays `new`, status `active`) when waiting on the agent to fill agent-side gaps

## Lead Card body format

Appended to the case file under `## Lead Card · 01 · <date>`:

```
- Intent: <buying / selling / renting>
- Budget: <range>, <financing status>
- Timeline: <close by / move in by>
- Location: <ZIP codes or neighborhoods>
- Constraints: <bed/bath/yard/schools/walkability/etc>
- Source: <lead source>
- Why moving: <if known>

**Unknowns:**
- <gap 1>
- <gap 2>
```

## Worked examples

See `examples.md`.
