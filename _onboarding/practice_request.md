# Step 3: Practice run

> **Voice profile in place? If not, complete `_onboarding/voice_capture.md` first** — this practice run uses your voice to draft a client email. Without it, you'll see a neutral fallback instead of the personalized output that demonstrates how the system actually feels.

## What this is

A canned new-lead intake you walk through end-to-end. You'll see all five specialists work in sequence: 00 routes → 01 qualifies → 02 researches → 03 drafts in your voice → 04 takes over when the deal goes under contract. Total run: ~10 minutes.

Your practice case file lives at `_shared/cases/_practice/<your-case-id>.md` — it stays out of the real caseload. Review it after the run, keep it as long as you want, delete when done.

## Paste this into the chat

Copy everything in the block below and paste it into Claude:

```
Practice intake — I'm new and running through onboarding.

Got a buyer lead at Saturday's Hyde Park open house. Marcus Patel.
Looking for a 3BR around $850K, wants to stay in 78751 or
78704. Pre-approved through Capital One — written letter expected
this week. Needs to close before October (lease ends Sept 30).
Wants walkability and a small yard.
```

## What to watch for

As you walk through the flow, look for:
1. 00 announces it's routing this as an onboarding practice run, and the case file goes to `_shared/cases/_practice/` (not the main caseload)
2. 01 takes the intake, prompts for any missing fields conversationally, then appends the Lead Card to the case file
3. 02 produces a Property Brief (comp worksheet + neighborhood notes + recommended angle)
4. 03 drafts a first-conversation email **in your voice** (verify it actually sounds like your interview)
5. (Optional — fast-forward) Tell Claude "Marcus accepted an offer at $830K, effective today" to trigger 04 — Deal Jacket goes in the case file

After the run, open `_shared/cases/_practice/<your-case-id>.md` and read through. That file is what your work looks like to the rest of the team.

## When you're done

You're operational. Shadow Diana on one real active deal next; that's the real on-ramp.
