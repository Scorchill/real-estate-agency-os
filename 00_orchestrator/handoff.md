# 00_orchestrator — Handoff

## What I accept

The user's raw message (and recent conversation history, and the relevant case file if a case_id is in context). I don't accept handoffs from other specialists — I'm the front door.

## What I produce

A chat header (per `rules.md` — chat header format, with full envelope details in root `HANDOFF_PROTOCOL.md`) followed by the specialist's response (or, for caseload queries / onboarding / anti-handoffs, my own direct response). When work moves to a case file, a trail entry is appended to the case file's Handoff trail section per `HANDOFF_PROTOCOL.md`.

## Trail entry format

When routing to a specialist on an active case, append to `_shared/cases/<case_id>.md` Handoff trail:

```
<date> 00 → <specialist> · "<one-line rationale>"
```

For anti-handoff terminal:

```
<date> 00 → human (no-prep) · "<reason>"
```

For onboarding (no case_id): no trail entry — onboarding lives outside the case-file system.

For caseload queries (no routing): no trail entry — read-only operation.

## Worked examples

See `examples.md`.
