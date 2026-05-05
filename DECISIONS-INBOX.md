# DECISIONS-INBOX

Live queue of cross-cutting decisions awaiting LAF-00 parent resolution. See `README.md` for conventions.

**Last updated:** 2026-05-02 LAF-00.12 close (post LAF-01.09 escalation absorption)
**Next parent session:** LAF-00.13 (TBD post-polling, unless urgent)

---

## Resolved this session (LAF-00.12) — kept visible for one session as audit trail

### DQ-STRAT-22 — Council vs ward as primary deliverable
**Raised:** 2026-05-01 LAF-03.01 (surfaced via post-LAF-00.11 side-note)
**Trigger:** Live SRUK site renders OG images at council level (`/local/{council}/`), not ward level.
**Scope impact:** LAF-01, LAF-03, LAF-04, LAF-05, LAF-06
**Status:** RESOLVED
**Resolution:** Council-level is primary deliverable. Ward-level demoted to "bespoke on demand" – generated for big urban councils, high-stakes wards Becky/Tom flag, or post-launch reactive content. Ward Wave 1 sourcing continues as input library for council-level selection. (LAF-00.12)

### DQ-STRAT-21 — Codebase migration to Git
**Raised:** ~2026-04-21 (Tom open intent), reraised 2026-05-01
**Status:** RESOLVED IN PRINCIPLE
**Resolution:** Promoted from "open intent" to "planned, post-7-May." Scope draft to follow post-election. Part B §19 updated. (LAF-00.12)

### DQ-DATA-01 — D4D recommendations for Senedd constituencies
**Raised:** 2026-05-02 LAF-00.12
**Status:** RESOLVED
**Resolution:** Wales recommendation = "heart recommendation": vote any of Green / Lib Dem / Labour / Plaid Cymru, with GOTV + share emphasis. D4D coverage confirmed by LAF-01.09 Gate 0 (16 Senedd constituencies present under `wac` slug). See DQ-STRAT-24 for content-template implications. (LAF-00.12)

### DQ-DATA-02 — D4D recommendations for Scottish AMS regions
**Raised:** 2026-05-02 LAF-00.12
**Status:** RESOLVED
**Resolution:** D4D coverage confirmed by LAF-01.09 Gate 0 — 8 Holyrood regions present under `sp` slug, GSS S17000021–28 (post-2026-review boundaries). (LAF-00.12)

### DQ-PROCESS-01 — Surface upstream-scope-changing facts immediately
**Raised:** 2026-05-02 LAF-00.12
**Status:** RESOLVED
**Resolution:** This inbox repo (`https://github.com/tdg/LAF-experimental-inbox`) is the resolution mechanism. Adopted in Part B v4.7 §20. (LAF-00.12)

### DQ-IMG-29 — Filename normalisation for mixed Welsh GSS formats
**Raised:** 2026-05-02 LAF-01.09 (originally raised as DQ-IMG-28; renumbered to avoid collision with parent's storage-migration DQ-IMG-28)
**Trigger:** D4D returned 4 Welsh constituencies with `W09xxxxxx` GSS codes and 12 with `senedd:slug-format` values; LAF-01.09 proposed strip-prefix normalisation for filename consistency.
**Scope impact:** LAF-01.09 sourcing, all downstream Welsh asset pipelines
**Status:** RESOLVED
**Resolution:** No filename-convention amendment. Re-resolve the W-codes first. Democracy Club Elections has `W09xxxxxx` codes for **all 16** Senedd constituencies (verified: Casnewydd Islwyn = `gss:W09000054`). The `senedd:` colon-form values are DC ballot-ID slug references, not GSS substitutes. The 4-vs-12 split is a D4D data-layer artefact (likely a missing or wrong join), not pre-GSS gaps. **Action for LAF-01.09:** before Gate 0.5, re-query D4D for the proper W-codes via the DC reference, or fetch directly from DC's elections API (`elections.democracyclub.org.uk/elections/senedd.{slug}.2026-05-07/`). All 16 Welsh constituencies follow standard form: `LAF-01-images-[slug]-W09xxxxxx-[variant].ext`. (LAF-00.12)

---

## Open items

### DQ-IMG-23 — Old Warley council attribution mismatch
**Raised:** 2026-05-02 LAF-01.08
**Trigger:** Brief documentation said Walsall, manifest + GSS confirmed Sandwell.
**Provisional assumption:** GSS authoritative; image and manifest reflect Sandwell.
**Decision needed by:** Non-blocking.
**Status:** OPEN

### DQ-IMG-25 — Constituency-level Scotland (73 spc)
**Raised:** 2026-05-02 LAF-01.09 (originally parked in LAF-00.11 brief; resurfaced)
**Trigger:** D4D has 73 Scottish Parliament constituencies (spc) for 2026-05-07. LAF-01.09 proposed swing at top 20 most competitive at close-of-session if margin.
**Scope impact:** LAF-01.09
**Provisional assumption:** Out of scope for this cycle. Per Tom: SNP competitive across most 73; progressive party so tactical-vote calls would be sparse and counterproductive. Pluralism leverage is in regional list. Do not reopen even with margin. If LAF-01.09 has spare capacity at close, prefer: more photos per region (15→20), bilingual Welsh A/B coverage, or boundary verification work.
**Decision needed by:** Confirmed at LAF-00.12 — ruling stands.
**Status:** OPEN — kept visible because it's a recurring temptation; surface for next-cycle planning.

### DQ-IMG-26 — Sourcer per-area distance/cluster params for larger geographies
**Raised:** 2026-05-02 LAF-01.09
**Scope impact:** LAF-01.09 only
**Status:** OPEN — owned in LAF-01.09 (child-scoped, not cross-cutting)

### DQ-IMG-27 — Bilingual Welsh search queries
**Raised:** 2026-05-02 LAF-01.09
**Trigger:** 12 of 16 Welsh constituencies have Welsh-primary names (DBCC determination).
**Provisional assumption:** A/B before full run, higher priority.
**Status:** OPEN — owned in LAF-01.09 (child-scoped); recommend keep-priority because heart-recommendation copy may also need bilingual Welsh, decision pending under DQ-STRAT-24.

### DQ-IMG-28 — Image storage migration & live-upload pattern
**Raised:** 2026-05-01 (post-LAF-00.11 side-note)
**Trigger:** Local outputs require laptop to stay on for downstream consumers.
**Provisional assumption:** Wave 1 continues writing to local. Don't delete or move outputs directory until storage decision made.
**Decision needed by:** Non-blocking pre-polling. Adam Hodgkin to advise on backend.
**Status:** OPEN
**Notes:** Council pivot shrinks scope: ~136–137 council images at ~30MB total, not 15,000 ward at ~3GB.

### DQ-STRAT-23 — LAF filename convention review (raised by Claude Code)
**Raised:** 2026-05-01 LAF-03.01 close-of-session
**Trigger:** CC noted inconsistencies in filename convention application.
**Provisional assumption:** Existing convention `LAF-NN.SS-[workstream]-[description].ext` continues until reviewed.
**Decision needed by:** Non-blocking.
**Status:** OPEN
**Notes:** Originally numbered DQ-STRAT-21 by CC, renumbered to avoid collision. The Welsh-filename variant earlier folded into this DQ has been resolved out of scope by DQ-IMG-29 — standard form holds for all 16.

### DQ-STRAT-24 — Wales "heart recommendation" content template
**Raised:** 2026-05-02 LAF-00.12
**Trigger:** Wales recommendation is structurally different from England/Scotland – four-party bloc + GOTV/share emphasis.
**Scope impact:** LAF-01.09, LAF-03, LAF-04, LAF-05, LAF-06
**Provisional assumption:** Wales content uses bloc-message template across all 16 constituencies. Visual single-landmark per constituency; copy lists all four parties; CTAs emphasise GOTV + share.
**Decision needed by:** Before any Wales content ships.
**Status:** OPEN
**Notes:** Bilingual (Welsh/English) copy decision also pending – flagged in LAF-01.09 brief and DQ-IMG-27.

### DQ-VID-01 — Sound for video pipeline
**Raised:** 2026-05-02 LAF-00.12
**Provisional assumption:** LAF-04.02 ships with silent track. Sound strategy resolved in a short follow-up session.
**Decision needed by:** Before any wide council-video batch ships.
**Status:** OPEN
**Action:** Spawn short sound strat session for CC-licensed shortlist + scoping summary.

### DQ-OG-01 — Reframe OG Issue: Phase 1 council swap, Phase 2 ward future scope
**Raised:** 2026-05-02 LAF-00.12 (from CC handoff)
**Provisional assumption:** Reframe required before posting.
**Decision needed by:** Sun 3 May 20:00 UTC if posting this weekend.
**Status:** IN PROGRESS – kickoff brief produced and posted to CC LAF-03 window 2 May 2026.

### DQ-VID-02 — Council ward-count assumptions in briefs
**Raised:** 2026-05-03 LAF-04.02
**Trigger:** LAF-04.02 brief assumed Adur has 8 wards ("Adur (8 wards, fits cleanly in one or two frames)"). D4D returned 14 wards (E05007562–E05007575 contiguous), 13 with tactical recs + 1 without (Marine). Multi-frame split was always the planned format so the discrepancy didn't change render strategy, but it does indicate that hand-authored ward-count facts in council-pivot briefs aren't reliable.
**Scope impact:** LAF-04 brief authorship for council format; LAF-05 council manifest (when built)
**Provisional assumption:** D4D is authoritative for ward roster per council. LAF-04.02 produced 2-frame Adur video (7+6) covering the 13 wards with recs; Marine omitted per brief's "all wards with recommendations" framing.
**Decision needed by:** Before any further council briefs are authored — convention should be "query D4D for the ward roster, don't assume from memory".
**Status:** OPEN

### DQ-VID-03 — Council video: handling wards with no D4D recommendation
**Raised:** 2026-05-03 LAF-04.02
**Trigger:** Adur's Marine ward (E05007568) has a contested ballot with locked candidates but no recommendation row in D4D. Algorithm hasn't produced one — likely pending and may resolve before polling.
**Updated 2026-05-04 LAF-04.02 per Tom:** "no recommendation" is a multi-case category — the council format needs a stable convention before batch council production. May want unified copy that works for all variants, or per-case copy.

**Variants observed or implied by D4D schema (`recommendations.reason_code` + missing-row case):**

| Case | Description | D4D signal |
|------|-------------|-----------|
| **A. Pending** | Algorithm hasn't produced a recommendation row yet (likely most common). | No row in `recommendations` for the ballot. *Marine ward — current case.* |
| **B. Heart recommendation (vote freely)** | Multi-party progressive bloc; any choice is fine. | `reason_code` = `VOTE_WITH_HEART_NO_REGRESSIVES`, `VOTE_WITH_HEART_REGRESSIVE_CANT_WIN`. *Wales-wide baseline – DQ-STRAT-24.* |
| **C. Cancelled / uncontested** | No vote possible or no contest. | `reason_code` = `CANCELLED`, `UNCONTESTED`, `NO_CANDIDATES_FOUND`, `CANDIDATES_UNLOCKED`. |
| **D. Algorithm declined (tactical)** | Tactical call too uncertain or impossible from data. | `reason_code` = `NEXT_RECOMMENDATION_TOO_CLOSE_TO_CALL`, `INDEPENDENT_IS_NEXT_BIGGEST`, `SMALL_PARTY_IS_NEXT_BIGGEST`, `NEXT_BIGGEST_PLACED_TOO_LOW_PREVIOUSLY`, `ONLY_REGRESSIVES_STANDING`, `NO_PREVIOUS_ELECTIONS_FOUND`, `LAST_ELECTION_MISSING_VOTE_COUNTS`. |

**Options for council video copy:**

1. **Unified "Check site"** (currently implemented for case A) — defers to live site for the user-friendly explanation. Single label across A/B/C/D. Lowest risk, highest abstraction. Tom's preferred direction "unless we can come up with copy that works for all".
2. **Differentiated labels** — e.g. A → "Pending"/"TBC", B → "Vote your heart"/"Multi-party", C → "Cancelled"/"No vote", D → "No clear lead". Requires per-case copy review and a `reason_code → label` mapping table.
3. **Hybrid** — unified "Check site" for v1 batch; differentiated copy for v2 once category usage is known across the ~136-council corpus.

**Research action item for parent (LAF-00.13 or sooner):**
- Audit `reason_code` distribution across all 7 May 2026 ENG locals — count rows per code in `recommendations`, plus count of ballots with no rec row at all. Tells us whether differentiated copy is worth the design cost or a unified label suffices.
- Confirm Wales heart-rec is its own format track (DQ-STRAT-24) — those constituencies probably don't appear inside English-council videos, so case B may be moot for the ENG council batch but live for Welsh constituency-level videos.
- Decide policy.

**Provisional assumption:** Universal "Check site" for case A only (current behaviour for Marine). Cases B/C/D will be handled when first encountered. Composition's discriminated-union row type leaves room for new kinds without breaking existing tactical rendering.
**Decision needed by:** Before batch council production.
**Status:** OPEN — research action pending parent.

### DQ-VID-04 — Council video background treatment
**Raised:** 2026-05-03 LAF-04.02
**Trigger:** Council videos cover N wards, so any single landmark photo would be arbitrary across the set. v1 used solid black; visually sparse next to ward videos which carry full landmark imagery.
**Scope impact:** LAF-04 council visual identity, all ~136–137 councils
**Provisional assumption (updated 2026-05-04 LAF-04.02 per Tom):** Background = best-scored landmark photo across all wards in the council, selected by LAF-01 sourcer score (highest `score=` value across rank-2..5 photos in the council's manifest rows). For Adur, this is Widewater photo-1, score 9.0. WardVideo-style treatment (full-frame cover, 0.85 opacity) with a darker scrim than ward template (`rgba(0,0,0,0.55) → 0.7 → 0.6`) to support the higher text density of council content. Photo attribution surfaces in the end card.
**Options now superseded:**
- ~~A) Solid black + subtle gradient (initial v1).~~
- ~~B) Tile/montage of all ward photos as background.~~
- C → adopted with refinement: best-of-geography rather than council-hero (avoids needing a separate LAF-01 council-level imagery pass).
- ~~D) Animated palette wash.~~
**Decision needed by:** Before batch council production.
**Status:** OPEN — provisional updated; awaiting parent close.
**Note for LAF-01/LAF-05:** "best photo across council" needs a stable selection rule when batched — currently it's "highest `score` value in `sourcing_notes` across all wards' rank-2..5 photos". Worth pinning convention in LAF-05 manifest.

### DQ-VID-05 — Short "all wards" council-video variant for monolithic-rec councils
**Raised:** 2026-05-04 LAF-04.02
**Trigger:** South Cambridgeshire (E07000012) renders as a 14-second 4-page video listing 26 wards — all of which recommend Liberal Democrat. The per-ward detail is identical for every viewer; the same message ("vote LD") repeats 26 times. A shorter "vote LD across South Cambridgeshire" variant would communicate the same information in 4–6 seconds, with stronger social-media legs and lower viewer cost.
**Scope impact:** LAF-04 format spec (two variants vs one); LAF-05 manifest (flag councils as monolithic-rec vs mixed); LAF-06 distribution (which variant to seed)
**Provisional assumption:** None yet — flagged for parent. v3 LOCKED format renders all wards regardless of homogeneity (current behaviour).
**Sketch of options:**
- A) **Per-council classification.** LAF-05 manifest tags each council `monolithic-rec | mixed-rec | partial-no-rec`. LAF-04 renders the appropriate variant: short "all wards LD" for monolithic, full ward-by-ward for mixed, mixed-with-Check-site for partial-no-rec.
- B) **Full ward video for everyone, optional short variant additionally for monolithic.** Both produced; distribution decides.
- C) **Defer.** Ship v3 LOCKED universally; revisit if seeding feedback shows the long format underperforms for monolithic councils.
**Threshold question:** at what mix does "monolithic" become "mixed"? 100% same party, or ≥90%, or ≥80%? E.g. if 25/26 wards are LD and 1 is GRN, does it count as monolithic? (Tactical answer might be: include the dissenting ward in the short version to avoid misleading that one ward's voters.)
**Decision needed by:** Before batch council production. Non-blocking for v3 LOCKED proof renders.
**Status:** OPEN — note for parent (LAF-00.13).

### DQ-STRAT-25 — Part B §14 session-log drift on LAF-04.02 row
**Raised:** 2026-05-03 LAF-04.02 (drift check at session open per Part B §15.3)
**Trigger:** Part B v4.7 §14 still lists LAF-04.02 next-pickup as "60-video three-bucket batch (best images / tightest contests / Reform defences) × 3 variants = 180 MP4s. Local in Claude Code". This was the LAF-00.11-era scope; LAF-00.12 rescoped LAF-04.02 to ward batch + council paper-edit (recorded correctly in Part A §8 and the LAF-04.02 kickoff brief). LAF-04.01 row's next-pickup line carries the same stale reference.
**Scope impact:** Operating model bookkeeping
**Provisional assumption:** Stale text doesn't change LAF-04.02 conduct (which followed the new kickoff brief). Surfaced per drift-check protocol; correction folds into next LAF-00.NN's Part B update.
**Decision needed by:** Whenever — non-blocking, fold into next Part B revision.
**Status:** OPEN

### DQ-DATA-02 — FOLLOW-UP — Scotland AMS regions: zero published recommendations
**Raised:** 2026-05-02 LAF-01.09 (after parent's RESOLVED ruling on ballots-present)
**Trigger:** Original DQ-DATA-02 resolved on D4D ballot presence (8 Scotland regions confirmed under `sp` slug). LAF-01.09 fact-check then found 0 published rows in `recommendations` for any of the 8 regions.
**Scope impact:** LAF-01.09 (speculative sourcing decision pending answer), all downstream Scotland workstreams
**Provisional assumption:** Tom 2026-05-02 — fire LAF-01.09 Scotland sourcing speculatively on the assumption recs land before 7 May. If LAF-05 confirms recs not coming, halt and reallocate.
**Decision needed by:** ASAP — every hour of speculative sourcing risks producing assets that ship nowhere. Target: pre-Sun 3 May 12:00 UK.
**Status:** OPEN
**Action:** Escalation ping drafted for LAF-05 / D4D team — see `LAF-01.09-images-escalation-ping-laf05.md` in handover pack.

### DQ-DATA-03 — Afan Ogwr Rhondda heart-rec missing
**Raised:** 2026-05-02 LAF-01.09
**Trigger:** During Wales D4D fact-check, 15 of 16 Senedd constituencies had heart-rec rows published (4 parties × 6 seats = 24 rows each, status `publish`). Afan Ogwr Rhondda (W09000048) has 0 rows.
**Scope impact:** LAF-01.09 (sourcing proceeds anyway), LAF-04 Video, LAF-03 OG, LAF-06 Distribution — anything downstream of Wales recs would skip this constituency until the rec lands.
**Provisional assumption:** Source images for the constituency normally. Asset bundle is held until rec lands; ship together once available.
**Decision needed by:** Pre-polling. If rec doesn't land by Wed 6 May, LAF-04/03 skips this one.
**Status:** OPEN
**Action:** Escalation ping drafted for LAF-05 / D4D team.

### DQ-DATA-04 — Blaenau Gwent Caerffili Rhymni: stale tactical drafts alongside heart publish
**Raised:** 2026-05-02 LAF-01.09
**Trigger:** Constituency W09000050 has both `rec_type='heart'` rows (status `publish`) and `rec_type='tactical'` rows (status `draft`) in `recommendations`. Tactical drafts likely stale from pre-heart-pivot work.
**Scope impact:** Cleanup ask only. Doesn't affect LAF-01.09. Could affect LAF-04/03/06 if any consumer queries `recommendations` without filtering by `status='publish'`.
**Provisional assumption:** Filter by `status='publish'` in all consumer queries; flag for cleanup but don't block on it.
**Decision needed by:** Non-blocking; cleanup at LAF-05's convenience.
**Status:** OPEN
**Action:** Mentioned in LAF-05 / D4D escalation ping.

### DQ-DATA-05 — D4D `gss_code` placeholder values for 12 of 16 Welsh constituencies
**Raised:** 2026-05-02 LAF-01.09
**Trigger:** During LAF-01.09 fact-check, D4D's `areas.gss_code` column returned `senedd:slug-format` strings (e.g. `senedd:bangor-conwy-mon`) for 12 of 16 Welsh Senedd constituencies. Only 4 had proper `W09xxxxxx` codes (Ceredigion Penfro / Clwyd / Gwynedd Maldwyn / Gŵyr Abertawe). Per parent's DQ-IMG-29 ruling, these are placeholder values, not pre-GSS gaps — Democracy Club's elections registry has proper W-codes for all 16.
**Scope impact:** Any LAF workstream querying D4D for canonical Welsh GSS codes. Surfaced first in LAF-01.09 but will hit LAF-04 Video, LAF-03 OG, LAF-06 Distribution, and SRUK if they query D4D for Welsh `gss_code`.
**Provisional assumption:** LAF-01.09 has worked around it: fetched correct W-codes from `elections.democracyclub.org.uk` (6 verified directly, 6 inferred from sequence W09000048–W09000063 alphabetical), all 16 published in handover-pack manifest stub.
**Decision needed by:** Non-blocking for LAF-01.09. Should be fixed in D4D before any other workstream runs into it.
**Status:** OPEN
**Action:** Escalation ping drafted for LAF-05 / D4D team — asks for either ingestion of correct W-codes into D4D, or documentation of the placeholder convention so future workstreams aren't blindsided.
---

## Action items pending from LAF-00.12

- [x] Inbox repo set up + initial commit
- [x] Slice 4 go-message conveyed to image session
- [x] LAF-03.02 OG-Issue-reframe kickoff brief produced and fired in CC
- [x] LAF-01.09 escalation absorbed — ruling on DQ-IMG-29 + reaffirmation of DQ-IMG-25 parked
- [x] LAF-04.02 kickoff brief produced
- [x] Part A v4.10 + Part B v4.7 produced
- [ ] Sound strat session brief – follow-up short session
- [ ] Tom to send LAF-01.09 escalation response back to that session (resume-and-direct)
- [x] Tom to fire LAF-04.02 *(fired 2026-05-03 in Claude Code; ward batch + council paper-edit + Adur proof rendered; close-of-session report at `~/Downloads/ward-videos/LAF-04.02-video-close-of-session-report.md`)*

---
