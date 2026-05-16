# 04_transaction_coordinator — Examples

Four worked scenarios: initial Deal Jacket build (a), a deadline-risk flag during option period (b), a title issue that triggers a comms loop to 03 (c), and a closing-day 04 → close handoff (d).

Each scenario opens with the chat header, shows the case file read at turn start, shows the Deal Jacket being written to the case file (not kept in chat), and shows the in-chat summary the agent actually sees.

---

## Scenario (a) — Deal goes under contract: initial Deal Jacket build

**Setup:** Tom's offer on 2105 Wilson St was accepted. 03 hands the acceptance to 04 via a `03 → 04` handoff. 04 reads the case file, builds the Deal Jacket in the case file's Deal Jacket section, and surfaces any tight items in chat.

**Chat header:**

```
**Transaction Coordinator — Sam Rodriguez (Tom)**
Offer accepted; building the initial Deal Jacket. *Case 2026-04-15-rodriguez*
```

**Case file read at turn start:** `_shared/cases/2026-04-15-rodriguez.md` shows Lead Card (buyer Sam Rodriguez, 78704, first-time buyer), Property Brief (2105 Wilson St analysis), and Comms log entries through offer acceptance. Deal Jacket section is empty (this is the first 04 turn). Header stage: `in-comms`; 04 will advance to `under-contract` on completion.

**Incoming `03 → 04` body (appended to the case file's Comms log / trail by 03):**

```
**Offer details:**
- Buyer: Sam Rodriguez
- Seller: Wilson Estate Trust
- Property: 2105 Wilson St, Austin TX 78704
- Accepted price: $702K (under list at $709K)
- Concessions: $3K toward closing costs

**Key dates** (verify against executed contract):
- Effective date: 2026-04-15
- Option period: 8 days (per contract paragraph 5)
- Earnest money: due per contract paragraph 5
- Financing contingency: 28 days (per financing addendum)
- Closing: 2026-05-30 (per contract paragraph 9)

**Open threads:**
- Final loan approval expected 5/20 per buyer's lender
- Seller's disclosure delivered before contract sign (verified)
```

**04's case-file write** — Deal Jacket section appended to `_shared/cases/2026-04-15-rodriguez.md`:

```markdown
## Deal Jacket  ·  04 · 2026-04-15

**Effective date:** 2026-04-15 (per executed contract)
**Closing date:** 2026-05-30 (per executed contract paragraph 9)

### Key dates (from contract — verify each)
- Option fee due: 2026-04-18 (per contract TREC 20-17 paragraph 5)
- Option period ends: 2026-04-23 (per contract TREC 20-17 paragraph 5; negotiated 8 days)
- Earnest money due: 2026-04-18 (per contract TREC 20-17 paragraph 5)
- Title commitment due: ~2026-05-05 (per contract TREC 20-17 paragraph 6 — confirm with title co)
- Financing contingency: 2026-05-13 (per financing addendum TREC TAR-1901; negotiated 28 days)
- Survey delivery: TBD (per contract TREC 20-17 paragraph 6 — negotiate with title co)
- Closing: 2026-05-30 (per contract TREC 20-17 paragraph 9)

### Doc status
- [x] Executed contract on file
- [ ] Option fee paid (due 2026-04-18)
- [ ] Earnest money paid (due 2026-04-18)
- [x] Seller's disclosure received
- [ ] Title commitment received (expected by 2026-05-05)
- [ ] Survey received
- [ ] Financing approval (expected by 2026-05-13)

### Who owes what
- Buyer (Sam): option fee + earnest money to title co by 4/18
- Lender: final loan approval to Tom by 5/13
- Title co: commitment to all parties by 5/5

### Open threads
- Final loan approval target 5/20 (per buyer's lender) — comfortably before closing
- Survey decision pending — Tom to confirm buyer wants own survey or accepts existing

### Risks surfaced (initial)
- Option period is 8 days — standard, no flag
- Closing is 45 days out — comfortable
```

**04's in-chat summary to Tom:**

> Deal Jacket built and saved to the case file. Looks routine: option fee and earnest money both due Friday (4/18), title commitment expected around 5/5, financing contingency 5/13, closing 5/30. I'll prompt you Wednesday if I don't see the option fee + earnest money confirmed. Want me to email title co about the existing-survey question on the buyer's behalf?

**Case-file updates:** header stage `in-comms → under-contract`; trail entry `2026-04-15 03 → 04 · "Offer accepted on 2105 Wilson St; initial Deal Jacket built"`.

---

## Scenario (b) — Pest inspection not scheduled, option period ends in 4 days (risk flag)

**Setup:** 04 does a routine Deal Jacket review on 2026-05-08 for an active deal on 3204 Clawson Rd (Sarah's buyer, Linda Torres). The option period ends 2026-05-12 — 4 days out. The Deal Jacket shows pest inspection not yet scheduled.

**Chat header:**

```
**Transaction Coordinator — Linda Torres (Sarah)**
Routine Deal Jacket review; pest inspection not yet scheduled. *Case 2026-04-28-torres*
```

**Case file read at turn start:** `_shared/cases/2026-04-28-torres.md` shows the active Deal Jacket section. Header stage: `under-contract`. 04 will update the Deal Jacket in place (the only mutable section beyond the header).

**04's case-file write** — updates to the Deal Jacket section of `_shared/cases/2026-04-28-torres.md`:

```markdown
## Deal Jacket  ·  04 · 2026-04-28  [Updated 2026-05-08]

**Effective date:** 2026-04-28 (per executed contract)
**Closing date:** 2026-06-06 (per executed contract paragraph 9)

### Key dates (from contract — verify each)
- Option period ends: 2026-05-12 (per contract TREC 20-17 paragraph 5; negotiated 14 days)
- Earnest money due: 2026-05-01 ✓ (per contract paragraph 5)
- Title commitment due: ~2026-05-18 (per contract TREC 20-17 paragraph 6)
- Financing contingency: 2026-05-26 (per financing addendum)
- Closing: 2026-06-06 (per contract paragraph 9)

### Doc status
- [x] Executed contract on file
- [x] Earnest money paid (confirmed 5/1)
- [x] General inspection complete (report received 5/5)
- [ ] Pest inspection — NOT scheduled
- [ ] WDI report received
- [ ] Title commitment received (expected by 5/18)

### Risks surfaced
- **FLAG (5/8) — Pest inspection not scheduled; option period ends 2026-05-12 (4 days)**
  - WDI (wood-destroying insect) report is a standard buyer contingency item
  - If not completed before option period ends, buyer loses the ability to walk on this basis
  - Scheduling typically takes 1–2 days; a tight window
```

**04's in-chat flag to Sarah:**

> Sarah — quick heads-up on the Torres deal. Pest inspection hasn't been scheduled and the option period ends Monday (5/12). That's 4 days, and most pest companies need 1–2 days to get out there. If Linda wants that inspection done inside the option period, she needs to call today or first thing tomorrow. Let me know when it's booked and I'll update the Deal Jacket.

No `04 → 03` comms handoff here — the action needed is the agent prompting the buyer to schedule an inspector, not a client email to draft. The Deal Jacket update is the case-file representation; chat is the surface.

If this had needed a client email (e.g., buyer wanted Sarah to write the pest company directly to escalate), the `04 → 03` handoff body would have looked like:

```
**Situation:** other (vendor escalation)
**Severity:** urgent
**Facts:**
- Pest inspection not yet scheduled; option period ends Monday 5/12 (4 days)
- WDI report required before option period close
- Two local providers contacted but no callback
**Recipient:** vendor (escalation to pest company)
```

`Severity: urgent` because of the clock, not because of strategic stakes.

---

## Scenario (c) — Title issue mid-deal: easement on title commitment (risk flag + comms loop to 03)

**Setup:** Title commitment comes back on 2026-05-05 for the Rodriguez deal (continuation of scenario a). Schedule B shows an unrecorded easement along the back fence line. 04 updates the Deal Jacket in the case file, surfaces the risk in chat, and emits a `04 → 03` handoff to get a client-facing email drafted for Sam.

**Chat header:**

```
**Transaction Coordinator — Sam Rodriguez (Tom)**
Title commitment received; Schedule B easement flagged. *Case 2026-04-15-rodriguez*
```

**Case file read at turn start:** `_shared/cases/2026-04-15-rodriguez.md` Deal Jacket shows option period expired ✓, earnest money paid ✓, financing contingency open. Header stage: `under-contract`. 04 updates the Deal Jacket in place.

**04's case-file write** — Deal Jacket section updated in `_shared/cases/2026-04-15-rodriguez.md`:

```markdown
## Deal Jacket  ·  04 · 2026-04-15  [Updated 2026-05-05]

**Effective date:** 2026-04-15 (per executed contract)
**Closing date:** 2026-05-30 (per executed contract paragraph 9)

### Key dates (from contract — verify each)
- Option period ends: 2026-04-23 ✓ (per contract TREC 20-17 paragraph 5; expired — buyer proceeded)
- Earnest money due: 2026-04-18 ✓ (per contract paragraph 5)
- Title commitment due: ~2026-05-05 ✓ (per contract TREC 20-17 paragraph 6; received on schedule)
- Financing contingency: 2026-05-13 (per financing addendum)
- Survey delivery: TBD (per contract paragraph 6)
- Closing: 2026-05-30 (per contract paragraph 9)

### Doc status
- [x] Executed contract on file
- [x] Option fee paid (confirmed 4/17)
- [x] Earnest money paid (confirmed 4/17)
- [x] Seller's disclosure received
- [x] Title commitment received (2026-05-05) — see open thread re: easement
- [ ] Survey received
- [ ] Financing approval (expected by 2026-05-13)

### Who owes what
- Buyer (Sam): no pending items; financing in progress
- Lender: final loan approval to Tom by 5/13
- Title co: provide documentation on Schedule B easement; potentially cure

### Open threads
- **NEW (5/5):** Unrecorded easement flagged in Schedule B — rear property line
  - Tom to decide: request seller cure, or confirm Sam/lender are comfortable
  - 03 drafting client-facing email explaining the issue (handed off 5/5)
  - Lender may surface this independently — Tom should loop with Sam's loan officer
- Survey decision pending — Tom to confirm

### Risks surfaced
- **FLAG (5/5) — Title encumbrance: unrecorded easement, rear property line**
  - Option period expired; buyer cannot walk without-cause
  - Lender may condition approval on easement documentation or cure
  - Seller cure (utility company release) typically takes 5–10 business days (estimate)
  - Closing date (5/30) is 25 days out — time to cure if started immediately
- Financing contingency 2026-05-13 — standard, no flag yet
```

**04's outgoing `04 → 03` handoff body** (per `HANDOFF_PROTOCOL.md` envelope):

```
**Situation:** other (title-commitment issue)
**Severity:** heads-up
**Facts:**
- Title commitment received 2026-05-05 (on schedule per contract paragraph 6)
- Schedule B exception: unrecorded easement, rear property line, utility access
- Option period expired 2026-04-23 — buyer past walk-without-cause
- Financing contingency open until 2026-05-13 — lender may flag this easement
- Seller can potentially cure via release or quitclaim from utility company
**Recipient:** buyer (Sam Rodriguez)
```

`Severity: heads-up` — Sam needs to understand the encumbrance exists; no alarm warranted. Severity sets cadence and tone for 03's draft; the strategic call (cure vs accept vs raise with lender) stays with Tom.

**04's in-chat summary to Tom:**

> Tom: Deal Jacket updated. Title commitment came back on schedule but Schedule B shows an unrecorded easement along the rear property line (utility access). I've sent a briefing to 03 to draft Sam's email — you'll get a draft to review shortly. Also worth a quick call to Sam's loan officer today to get ahead of this before underwriting. Do you want me to draft that framing for you as well, or handle it verbally?

**Case-file updates:** trail entry `2026-05-05 04 → 03 · "Title commitment Schedule B easement; needs buyer comms draft"`. Stage stays `under-contract`.

---

## Scenario (d) — Closing day: 04 → close handoff

**Setup:** The Mitchell deal (Diana's seller-side listing on 1418 Westview Ave) closed today, 2026-06-12. Final closing happened at title at 2pm; funds disbursed, deed recorded. Diana attended; 04 wraps the file.

**Chat header:**

```
**Transaction Coordinator — Frank Mitchell (Diana)**
Closing complete; finalizing Deal Jacket and emitting 04 → close. *Case 2026-05-02-mitchell*
```

**Case file read at turn start:** `_shared/cases/2026-05-02-mitchell.md` Deal Jacket shows all key dates met, all doc-status boxes checked, financing approval ✓, title clear, closing on calendar for today. Header stage: `under-contract`, status `active`. 04 will advance to `closed` / `won` on completion.

**04's case-file write** — final Deal Jacket updates in `_shared/cases/2026-05-02-mitchell.md`:

```markdown
## Deal Jacket  ·  04 · 2026-05-02  [Final update 2026-06-12 — CLOSED]

**Effective date:** 2026-05-02 (per executed contract)
**Closing date:** 2026-06-12 (per executed contract paragraph 9) ✓ CLOSED ON SCHEDULE

### Key dates (from contract — verify each)
- Option fee due: 2026-05-05 ✓ (per contract TREC 20-17 paragraph 5)
- Option period ended: 2026-05-12 ✓ (per contract paragraph 5; 10 days negotiated)
- Earnest money due: 2026-05-05 ✓ (per contract paragraph 5)
- Title commitment due: 2026-05-22 ✓ (per contract TREC 20-17 paragraph 6)
- Financing contingency: 2026-06-02 ✓ (per financing addendum)
- Survey delivery: 2026-05-28 ✓ (per contract paragraph 6)
- Closing: 2026-06-12 ✓ CLOSED

### Doc status (final)
- [x] Executed contract on file
- [x] Option fee paid (5/5)
- [x] Earnest money paid (5/5)
- [x] Seller's disclosure delivered pre-contract
- [x] Title commitment received and clear
- [x] Survey received
- [x] Financing approval (final 6/1)
- [x] Closing statement signed (6/12)
- [x] Deed recorded (6/12)

### Closing summary
- Final sale price: $912K (above list at $899K)
- Buyer: cash + financing mix (per closing statement)
- Closed-on date: 2026-06-12
- Side: seller (Diana represented Mitchell as listing agent)

### Post-close items
- [ ] Utility hookup coordination — N/A (seller-side; buyer handles)
- [ ] File archival — pending (move case to closed-deals archive per team practice)
- [ ] Optional: thank-you email to Frank Mitchell (handing to 03 if Diana wants)

### Open threads
- None — all items resolved
```

**04's outgoing `04 → close` handoff body** (per `HANDOFF_PROTOCOL.md` envelope; closes the lifecycle):

```
**Closing summary:**
- Final price: $912K (above list at $899K)
- Closed-on date: 2026-06-12
- Side: seller (Diana / listing)

**Post-close items:**
- File archival — pending (move case to closed-deals archive)
- No utility hookup coordination (seller-side)

**Optional next:** hand to 03 to draft a thank-you / nurture email to Frank Mitchell if Diana wants one.
```

**Case-file header updates:** stage `under-contract → closed`, status `active → won`. Trail entry `2026-06-12 04 → close · "Mitchell closed at $912K above list; final Deal Jacket updates posted"`.

**04's in-chat summary to Diana:**

> Diana: Mitchell closed clean at $912K — Deal Jacket finalized, stage marked closed/won, trail entry posted. Want me to hand to 03 for a thank-you draft to Frank? You usually send one a week out; let me know if you'd prefer the standard cadence or something different this time.

**Optional follow-on `04 → 03` (if Diana wants the thank-you):**

```
**Situation:** other (closing thank-you / nurture)
**Severity:** routine
**Facts:**
- Mitchell deal closed 2026-06-12 at $912K (above list $899K)
- Diana represented listing-side; relationship warm throughout
- Standard Diana cadence: thank-you ~1 week post-close
**Recipient:** seller (Frank Mitchell)
```

`Severity: routine` — no clock, no risk, just a nurture touch. Diana decides to send or pass.

---

*Reference:* See `handoff.md` for `03 → 04`, `04 → 03`, and `04 → close` body formats; `rules.md` for Deal Jacket structure and risk-flag thresholds; `HANDOFF_PROTOCOL.md` (root) for envelope and lifecycle details.
