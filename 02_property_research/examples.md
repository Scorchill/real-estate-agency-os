# 02_property_research — Examples

## Scenario 1: Comps for a qualified lead — happy path

This scenario picks up where 01's Scenario 1 leaves off. The trail entry `01 → 02` for Alfred Gardener has landed; 02 reads the case file, appends a Property Brief, and routes to 03 for the first-conversation email.

**Context:** Case `2026-05-13-gardener` exists at stage `qualified`, status `active`, owning agent Bob. Lead Card from 01 captures: buyer, $650K–$725K, pre-approved Frost Bank, 78704 primary / 78745 acceptable, fenced yard + walkability required, no flips, close by mid-August.

**02 responds** (after 00's chat header routes to Property Research):

```
**Property Research — Alfred Gardener (Bob)**
Intake just completed; comps and school zones next. *Case 2026-05-13-gardener*
```

Reading `_shared/cases/2026-05-13-gardener.md` — Lead Card from 01 yesterday is the basis. No prior Property Brief; this is the first.

Market read done. 78704 inventory under $725K is thin and the fenced-yard requirement cuts it further. 78745 has more options but walkability will suffer. Comp worksheet below with MLS search parameters — Bob should pull and fill before the first client conversation.

Note: 02 runs in a markdown system without live MLS access. The comp table is a worksheet with the exact parameters to run; it is NOT a table of confirmed listings. Active listings may be web-verified (Zillow/Redfin, cited); sold prices require MLS (Texas non-disclosure).

Appending to the case file under `## Property Brief · 02 · 2026-05-13`:

```
**Summary:** 78704 inventory under $725K is thin — typically fewer than 4 active
listings at any time in this ZIP, and the fenced-yard requirement cuts that
further. 78745 has more breathing room and more sqft per dollar, but walkability
scores drop significantly. Suggested first-conversation framing: 78704 means a
short list and fast decisions; 78745 is the fallback if Alfred can flex on
walkability.

**Comp worksheet parameters** (run in Unlock MLS):
- ZIPs: 78704, 78745
- Price: $620,000–$725,000
- Bed/Bath: 2 bed / 1 bath minimum
- Recency: active or closed within last 45 days
- Exclusions: no flips (permit history flag), no new construction

| Address | Status | Price | Sqft | Bed/Bath | Fenced yard? | Walk Score | Delta vs. target |
|---|---|---|---|---|---|---|---|
| *(ILLUSTRATIVE — not a real listing.)* | Active | $699K | 1,200 | 2/2 | Yes | 75 | Shows column format only |

Agent: pull 78704 and 78745 results from Unlock MLS and paste them back
here — or fill the table directly. Flag which have fenced yards (Alfred's
hard requirement). Active listings can also be cross-checked on Zillow/
Redfin for Walk Score (cite source). Sold prices require MLS — Texas is
a non-disclosure state.

**Neighborhood notes:**
- 78704: under 1 month supply, multi-offer common; expect to compete on pace
- 78745: balanced, ~2 months supply, less urgency; more sqft per dollar
- School zones (from austin_market_brief.md): Travis Heights / Zilker ES → Lively MS / Fulmore MS → Travis HS / Austin HS for 78704; Joslin / St. Elmo / Cunningham ES → Bedichek MS → Crockett HS for 78745 — verify current zones at austinisd.org
- Walkability: 78704 typically scores 70+ Walk Score; 78745 typically 30–50 (car-dependent)

**Recommended angle for first conversation:** Frame for Alfred as: "78704 means
urgency and tradeoffs — the fenced-yard requirement makes the list short. 78745
opens it up at the cost of walkability. Let's look at what MLS shows us and
decide together." Set expectations on pace before introducing specific listings.
```

Header stage updated `qualified → researched`. Last update bumped.

Trail entry appended: `2026-05-13 02 → 03 · "Market context done; first-conversation email next in Bob's voice"`

Then the chat header for 03 fires next turn:

```
**Client Comms — Alfred Gardener (Bob)**
First-conversation email; voice_bob.md present. *Case 2026-05-13-gardener*
```

---

## Scenario 2: One-off comp request

This scenario is a direct one-off routed by 00. No active deal context — a past client texted Tom asking what his house might sell for. 02 produces market analysis and a comp worksheet; next steps are up to the agent. No case_id, so nothing to read at turn start; no Property Brief appended to any case file.

**02 receives** the 00 routing for 4108 Avenue G, 78751 (Tom owning, one-off).

**02 responds:**

```
**Property Research — quick comp for 4108 Avenue G (Tom)**
Past-client one-off, no active deal.
```

No case_id in context — nothing to read. Producing the brief inline; no case file write.

Hyde Park market read done. Renovated bungalows in 78751 support $850K–$950K based on price-per-sqft norms — but that's a market-level estimate, not a confirmed value. MLS comp pull required to sharpen the range. Texas is a non-disclosure state — sold prices are not publicly accessible and must come from MLS.

**Summary:** Past client of Tom's texted asking what 4108 Avenue G (78751) might sell for. House is a 1940s bungalow, ~1,150 sqft, 2/1, fully renovated kitchen per Google Street View. Market read and comp worksheet below; MLS pull needed for confirmed comps.

**Comp worksheet parameters** (run in Unlock MLS):
- ZIP: 78751
- Price: $750,000–$1,050,000
- Bed/Bath: 2 bed / 1 bath minimum
- Style: bungalow / pre-1960 construction preferred for valid comparison
- Recency: closed or active within last 60 days
- Exclusions: no major additions that would distort sqft comparison

| Address | Status | Price | Sqft | Bed/Bath | Renovation level | Delta vs. subject |
|---|---|---|---|---|---|---|
| *(ILLUSTRATIVE — not a real listing.)* | Sold | $900K | 1,180 | 2/1 | Full reno | Shows column format only |

Agent: pull Hyde Park comps from Unlock MLS. For sold comps, MLS access is required — Texas is a non-disclosure state and sold prices from public sites (Zillow, Redfin) are not reliable. Active listings can be cross-checked on those sites (cite source if used). Fill the table and paste back if you want analysis.

**Neighborhood notes:** Hyde Park (78751) is mid-cycle per `austin_market_brief.md`: 2–3 months supply. Renovated bungalows at this sqft typically run ~$700/sqft; original-condition stock discounts 10–15% from that. Tom's client's renovation (kitchen at minimum) supports the upper part of the range — interior walk needed to confirm scope.

**Recommended angle for first conversation:** If Tom's client wants a number before an interior walk, $850K–$950K is a reasonable range to share — with the caveat that a walk is needed to confirm. If they're testing whether to list, mid-cycle is a viable moment but not a peak.

(No trail entry — one-off, no case file. Agent decides next step.)

---

## Scenario 3: Market-context question for an existing client

This scenario is a market-context question, not a comp pull. An agent asks about conditions in 78745 for an existing client who is deciding whether to list. No active case_id — the agent just wants context before a conversation.

**User pastes** (Sarah):
> I have a client in 78745 deciding whether to list this spring or wait until fall. She's not ready to give us an address yet — just wants to know if now is a good time to sell. What can I tell her?

**02 responds** (after 00's chat header routes to Property Research):

```
**Property Research — 78745 market context (Sarah)**
Pre-listing conversation prep; no active deal yet.
```

No case_id — nothing to read. Producing the read inline.

For a seller-side conversation in 78745 right now, here's the honest context:

**Market conditions — 78745 (mid-2026)**
- Supply is balanced: roughly 2–4 months of inventory. Not a seller's market, not a buyer's market. Sellers are getting close to list price on well-presented homes, but the days of bidding wars above ask are not the norm here.
- Typical price range for the ZIP is $500K–$900K. Family-oriented stock in the mid-range ($550K–$700K) is moving steadily; higher-end inventory is sitting longer.
- Spring listing window (April–June) historically outperforms fall for 78745 family homes — school-calendar buyers are active now. Fall will see a natural slowdown.
- If she waits until fall, she's betting that inventory drops further or buyer demand holds. Neither is certain. Spring is the more reliable window.

**What to tell her:**
- Spring gives her a timing edge over fall — buyer pool is larger now.
- "Balanced" means she should price at market, not above it. Overpriced listings in 78745 are sitting 45–60+ days right now.
- Once she's ready to share the address, we can pull a proper CMA with sold comps and a realistic list-price range.

No trail entry, no case file write — this is a context question, not a comp pull. When she's ready to share the address, route to 02 for a full listing-side CMA (which mints a case_id if it flows into an active deal, or produces a `02 → (agent decides)` one-off if she's still testing).

---

## Scenario 4: 02 → 01 back-edge (re-qualification on a mismatch)

This scenario shows the **02 → 01 re-qualification** transition defined in `HANDOFF_PROTOCOL.md` (Special transitions section). Buyer's stated budget can't realistically clear their stated location. 02 doesn't silently shift the search; it drops stage back to `qualified` with a divergence note and trail entry, so 01 re-engages.

**Context:** Case `2026-05-15-pennington` exists at stage `qualified`, status `active`, owning agent Sarah. Lead Card captures: buyer, budget up to $725K, pre-approved Frost Bank, location 78703 (Tarrytown), 3BR/2BA minimum, close by end of summer, relocating from Dallas.

**02 responds** (after 00's chat header routes to Property Research):

```
**Property Research — Joan Pennington (Sarah)**
Tarrytown comp read; flagging an apparent budget/location mismatch. *Case 2026-05-15-pennington*
```

Reading `_shared/cases/2026-05-15-pennington.md` — Lead Card from 01 (2026-05-15) is the basis. No prior Property Brief.

Pulling the 78703 (Tarrytown) read against the Lead Card. There's a hard mismatch: 78703 is one of Austin's most expensive ZIPs (typically $1.5M–$3M+ per `austin_market_brief.md`); 3BR/2BA inventory under $1.2M is effectively nonexistent. The $725K ceiling clears nothing in this ZIP at the stated bed/bath minimum. This isn't a "thin shortlist" — it's structurally outside the price band.

Not advancing stage. Dropping back to `qualified` and routing to 01 for re-qualification with the agent. Sarah needs to take this back to Joan: either the budget needs to expand to ~$1.4M+ to be in Tarrytown at 3BR/2BA, or the location needs to expand to ZIPs where $725K is realistic (78745, 78744, some 78704 fringe).

Appending to the case file under `## Property Brief · 02 · 2026-05-15`:

```
**Summary:** Budget/location mismatch surfaced on first read. 78703 (Tarrytown)
is one of Austin's most expensive ZIPs; 3BR/2BA inventory under $1.2M is
effectively nonexistent there. The stated $725K ceiling doesn't clear the ZIP
at the stated bed/bath minimum — this is structural, not a thin-supply issue.
Routing back to 01 for re-qualification with the agent before any comp pull
would produce useful output.

**Comp worksheet parameters** (NOT RUN — mismatch flagged first):
- ZIPs: 78703 (per Lead Card)
- Price: $620,000–$725,000 (per Lead Card)
- Bed/Bath: 3 bed / 2 bath minimum (per Lead Card)
- Recency: would have been last 60 days
- Exclusions: standard (no flips, no new construction)

(No worksheet table generated. Running the search at these parameters returns
zero or near-zero results; producing an "ILLUSTRATIVE" row would mislead.)

**Neighborhood notes:** 78703 typical price band is $1.5M–$3M+ per
`austin_market_brief.md`. The sub-$800K stratum in this ZIP is essentially
tear-down lots or rare condo inventory — not 3BR/2BA single-family. Comparable
budget would land in 78745 ($500K–$900K range), 78744 (similar), or 78704
fringe (tight but possible at $700K+ for smaller footprints, usually 2BR).

**Recommended angle for first conversation:** N/A — re-qualification needed
before a client conversation is productive.

**Divergence note (back-edge triggered):**
The Lead Card's combination of $725K ceiling + 78703 location + 3BR/2BA
minimum is structurally infeasible. 02 cannot produce a useful comp
worksheet at these parameters; running the search returns no matches and
the ILLUSTRATIVE-only worksheet would mislead Sarah into thinking the gap
is closeable with effort. Re-qualification needed: Sarah should clarify
with Joan whether budget can stretch to ~$1.4M+ (Tarrytown reality) or
whether location can expand to ZIPs where $725K is realistic (78745,
78744, 78704 fringe).
```

Header stage updated `qualified → qualified` (no advance; stays at qualified). Last update bumped.

Trail entry appended: `2026-05-15 02 → 01 · "re-qualification needed: $725K + 78703 + 3BR/2BA is structurally infeasible; agent should re-clarify budget OR location"`

Then the chat header for 01 fires next turn:

```
**Lead Qualifier — Joan Pennington re-qualification (Sarah)**
Budget/location mismatch surfaced in research; re-engaging. *Case 2026-05-15-pennington*
```

The 01 response that follows reads the case file, sees the divergence note in the Property Brief, and walks Sarah through the two-path conversation she needs to have with Joan: "either we widen the budget to roughly $1.4M to stay in Tarrytown, or we widen the location to 78745/78744 to keep $725K. Which feels right to push on?" Sarah goes back to Joan, gets the answer, pastes it back, and 01 updates the Lead Card; 02 then re-runs the brief against the corrected constraints.
