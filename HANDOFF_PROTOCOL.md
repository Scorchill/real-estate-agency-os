# Handoff protocol

The contract every specialist follows when work moves between folders: one case file per deal, one envelope schema per handoff, one lifecycle vocabulary. All five specialist folders' `handoff.md` and `rules.md` reference this file; folder-specific body content (Lead Card, Property Brief, Comms log, Deal Jacket) lives in those folders.

## The case file

One markdown file per deal at `_shared/cases/<case_id>.md`. Specialists read it at turn start when a case_id is in context and append on handoff; the header is the only mutable section. Survives context compression because it's a file, not a chat artifact.

**File structure:**

```markdown
# <case_id> · <client name>

**Stage:** new | qualified | researched | in-comms | under-contract | closed
**Status:** active | paused | won | lost
**Owning agent:** <name>
**Side:** buyer | seller
**Opened:** YYYY-MM-DD
**Last update:** YYYY-MM-DD HH:MM

---

## Lead Card  ·  01 · <date>
(appended when 01 completes intake)

## Property Brief  ·  02 · <date>
(appended when 02 completes research; may be re-appended if 02 re-runs with a new date)

## Comms log  ·  03
- <date> — <subject/situation> — drafted in <agent>'s voice; sent: <Y/N>
- (one bullet per draft, appended over time)

## Deal Jacket  ·  04
(empty until under-contract; full Jacket structure once 04 takes over)

## Handoff trail
1. <date> 00 → 01 · "<one-line brief>"
2. <date> 01 → 02 · "<one-line brief>"
...
```

**Append discipline:**
- Past sections are never rewritten; new entries append with dates.
- Header values (Stage, Status, Last update) are atomic-update fields.
- Owning agent changes only via explicit reassignment trail entry: `<date> <prior-owner> → <new-owner> · reassignment · "<reason>"`. This is the only mechanism for owning_agent changes — ad-hoc rewrites of the header field are not allowed.

**Read trigger:** at turn start when a case_id is in context — by direct paste, prior-turn handoff, or explicit user mention. New leads with no case_id: read happens after 01 mints the case_id and creates the file.

**Practice case variant:** onboarding practice runs write to `_shared/cases/_practice/<case_id>.md` (same structure, different location). Caseload queries skip underscore-prefixed subfolders by default — leaves room for future `_test/` or `_archive/` with the same skip rule.

## Case_id format

`YYYY-MM-DD-<slug>` — slug is 3–15 chars lowercase, hyphenated. Usually lastname; address fragment acceptable for unnamed leads. Collisions suffix `-2`, `-3`. Examples: `2026-05-13-gardener`, `2026-05-14-4108-ave-g`, `2026-05-14-mendez-2`.

## The handoff envelope

**Chat representation:** every specialist response opens with a bold header (specialist + client + owning agent), plus an italic line carrying the case_id when relevant. The header itself is the in-chat handoff signal — work moving 01 → 02 appears as 02's response opening with `**Property Research — Alfred Gardener (Bob)**`. No separate arrow-prefixed announcement line; the header alone is canonical. Three variants — active deal, one-off, caseload/onboarding/anti-handoff:

**Active deal:**

```
**Property Research — Alfred Gardener (Bob)**
Intake just completed; comps and school zones next. *Case 2026-05-13-gardener*
```

**One-off:**

```
**Property Research — quick comp for 4108 Avenue G (Tom)**
Past-client one-off, no active deal.
```

**Caseload query, onboarding, or anti-handoff** (same shape — bold descriptor of what's happening, optional italic context line, no case_id when there isn't one):

```
**Caseload view — Tom's active deals**
(no case_id; reads from _shared/cases/)
```

**Case-file representation (appended on handoff):**

*Pseudo-form below — the headings show where content lands, not literal output strings. Specialists produce the actual content per their folder's body format.*

```
Trail entry (appended to Handoff trail section):
<date>  <from> → <to> · "<one-line brief>"

Body (appended to the relevant specialist section — Lead Card, Property Brief, Comms log, Deal Jacket):
[structured content per that specialist's body format]
```

**Envelope fields:** Five structured (`case_id`, `from`, `to`, `stage`, `owning_agent`), plus a one-line `brief` and a 3–6 sentence body. The five structured fields are fixed — no additions. The brief and body are the free-text payload.

## Lifecycle and status

| Stage | Owner active here | Triggers next stage |
|---|---|---|
| `new` | 00 just routed | 01 completes intake |
| `qualified` | 01 done; 02 may be working | 02 produces Property Brief |
| `researched` | 02 done; ready for comms or showing | 03 produces first draft |
| `in-comms` | 03 active; client correspondence in motion | offer accepted → 04 |
| `under-contract` | 04 owns; option period through close | closing complete |
| `closed` | terminal | (status: won or lost) |

| Status | Meaning |
|---|---|
| `active` | currently working |
| `paused` | client cooled off; will revisit |
| `won` | closed-won (terminal) |
| `lost` | closed-lost (terminal) |

Caseload queries filter on either or both: *"active under-contract deals"*, *"closed-won past 90 days"*, *"all paused leads"*.

## Special transitions

- **02 → 01 (re-qualification):** Research surfaces a mismatch (e.g., budget vs. location). Stage drops back to `qualified` with a divergence note in the trail. 01 re-engages.
- **04 → close:** Deal closes. Stage → `closed`, status → `won` or `lost`. Optional hook to 03 for a nurture/thank-you draft.
- **Anti-handoff terminal:** 00 hits a scope boundary and no prep is wanted. Trail entry `<date> 00 → human (no-prep) · "<reason>"`. Stage and status unchanged.
- **01 → 03 (qualification follow-up):** Thin lead intake. 01 captures what's known, classifies missing fields as agent-side vs lead-side, and hands to 03 to draft a warm follow-up to the lead asking for the lead-side gaps. After agent sends and the lead replies, the agent pastes the reply; 00 routes back to 01 (which reads the existing case file at stage `new` and continues intake). Stage stays `new`, status `active` across the wait.

## Inter-agent write collision

Only the owning agent appends in a session. If two agents need to touch a case simultaneously, the second waits. Cases are rarely simultaneous in practice (one deal = one owning agent), so this is a discipline, not a lock.
