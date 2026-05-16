# When the system is offline

> **Single-vendor honesty.** This system depends on Claude Code being available. If it's down — an Anthropic outage, an internet outage, your laptop is dead — the team still has to function. This file is the paper-fallback reference for the work that can't wait.

## What this page covers

The three specialist outputs most likely to be deadline-critical:

1. **Lead intake** — capturing a new lead by hand
2. **Option-period worksheet** — tracking the key dates on an active deal
3. **Inspection-issue heads-up** — drafting a client email from scratch

## 1. Manual lead intake

When 01 can't process the lead, capture these fields on paper or in any note-taking tool. The structure matches what `_intake/buyer_TEMPLATE.md` and `_intake/seller_TEMPLATE.md` cover.

**Buyer intake (minimum viable):**
- Name + phone + email
- Buying or browsing (intent)
- Budget range + pre-approval status (lender + amount if known)
- Timeline (close-by date or move-in date)
- Location(s) of interest
- Bedrooms / property type / dealbreakers
- Lead source

**Seller intake (minimum viable):**
- Name + phone + email
- Property address
- Timeline to list
- Reason for selling
- Mortgage status (paid off / amount remaining)
- Target sale price (or "no idea yet")
- Lead source

When the system is back up, paste the captured intake into chat — 01 will create the case file and continue.

## 2. Option-period worksheet (TREC)

When 04 can't run, anchor on the **executed contract** — not on this file or any default. The contract is the source of truth for every date.

**Pull from the executed contract:**
- Effective date (last party signs + delivered)
- Option fee amount + due date (TREC 20-17 paragraph 5)
- Option period end date (negotiated; common range 5–10 days)
- Earnest money amount + due date (typically 3 days from effective unless modified)
- Financing contingency end date (TAR-1901 if used)
- Closing date

**Run by hand:**
- Has option fee been paid? (Y/N — confirm with title co)
- Has earnest money been delivered? (Y/N — confirm with title co)
- Are inspections scheduled to complete before option period ends? (Y/N)
- Is the seller's disclosure on file? (Y/N — if N, flag immediately)

When the system is back up, paste the worksheet — 04 will rebuild the Deal Jacket in the case file.

## 3. Inspection-issue heads-up (manual draft)

When 03 can't draft, the structural elements still hold (from `03_client_communication/rules.md`):

- **Heads-up framing** — no alarm
- **Plain statement of what the inspector saw** — facts only, no speculation
- **Next-step proposal** — structural engineer? renegotiation? walk?
- **Option-period clock if relevant** — without pressure

Write in your own voice. Keep it short. Open the call/text/email with the heads-up framing; close with the next step you're proposing.

When the system is back up, log the sent email into `_shared/cases/<case_id>.md` Comms log so the audit trail stays continuous.

## After an outage

When Claude Code is back:
1. Paste a quick recap of any deal activity that happened offline into the relevant chat
2. 00 routes to the appropriate specialist
3. Specialists update case files with the offline activity
4. Continue normally

The case files are the spine — once you're back, the system rebuilds state from what you paste.
