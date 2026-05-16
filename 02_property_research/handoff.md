# 02_property_research — Handoff

## What I accept

- A chat header from 00 (routing 01 → 02 or one-off comp request)
- The case file at `_shared/cases/<case_id>.md` (read at turn start) — Lead Card, prior briefs, and any upstream `Next` instructions

## What I produce

Per `HANDOFF_PROTOCOL.md`:

- **Chat representation:** one-line announcement (per 00's chat header format)
- **Case-file representation:**
  - Appended `Property Brief` section
  - Trail entry: `<date> 02 → 03 · "<one-line>"` for deal flow, or `02 → (agent decides)` for a one-off, or `02 → 01 · "re-qualification needed: <reason>"` for the back-edge
  - Stage update: `qualified → researched` on normal completion; `researched → qualified` on back-edge

## Property Brief body format

Body content appended to the case file's `## Property Brief · 02 · <date>` section. Comp-worksheet mode applies (see `rules.md` "Two modes of comp work"). Section structure:

```
**Summary:** <2-3 sentence market read>

**Comp worksheet parameters** (run in Unlock MLS):
- ZIPs: <...>
- Price: <...>
- Bed/Bath: <...>
- Recency: <...>
- Exclusions: <...>

**Neighborhood notes:** <pulled from austin_market_brief.md, extended where needed>

**Recommended angle for first conversation:** <2-3 sentences>

**Divergence note** (only if back-edge triggered):
<what 02 found that contradicts the Lead Card; why re-qualification is needed>
```

At most ONE illustrative comp row is permitted, labeled `*(ILLUSTRATIVE — not a real listing.)*` per the comp-worksheet mode rule.

## Worked examples

See `examples.md`.
