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
**Trigger:** Adur's Marine ward (E05007568) has a contested ballot with locked candidates but no recommendation row in D4D. Algorithm hasn't produced one — likely pending and may resolve before polling. Brief originally framed "all wards with recommendations"; subsequent direction was to render all wards but mark the no-rec case clearly.
**Scope impact:** LAF-04 council format spec; LAF-05 manifest definition; LAF-03 (parallel issue for OG copy)
**Provisional assumption (updated 2026-05-04 LAF-04.02 per Tom):** Include all wards. For wards with no D4D recommendation *row*, render a "Check site" pill (neutral white-outlined fill, distinct from party pills) directing the voter to look up the ward live, since the recommendation may resolve before polling. Other no-rec variants — heart-recommendation abstentions, ONLY_REGRESSIVES, VOTE_WITH_HEART_NO_REGRESSIVES, uncontested wards — need separate copy decisions and will be handled when first encountered (composition's discriminated-union row type leaves room).
**Options now superseded:**
- ~~A) Omit (initial v1 behaviour).~~
- B) Include with no-rec callout — chosen, with "Check site" copy.
- ~~C) "(no contest)" badge — rejected as potentially misleading.~~
**Decision needed by:** Before batch council production — confirm "Check site" copy + extend to other no-rec variants as they appear.
**Status:** OPEN — provisional updated; awaiting parent close.

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

### DQ-STRAT-25 — Part B §14 session-log drift on LAF-04.02 row
**Raised:** 2026-05-03 LAF-04.02 (drift check at session open per Part B §15.3)
**Trigger:** Part B v4.7 §14 still lists LAF-04.02 next-pickup as "60-video three-bucket batch (best images / tightest contests / Reform defences) × 3 variants = 180 MP4s. Local in Claude Code". This was the LAF-00.11-era scope; LAF-00.12 rescoped LAF-04.02 to ward batch + council paper-edit (recorded correctly in Part A §8 and the LAF-04.02 kickoff brief). LAF-04.01 row's next-pickup line carries the same stale reference.
**Scope impact:** Operating model bookkeeping
**Provisional assumption:** Stale text doesn't change LAF-04.02 conduct (which followed the new kickoff brief). Surfaced per drift-check protocol; correction folds into next LAF-00.NN's Part B update.
**Decision needed by:** Whenever — non-blocking, fold into next Part B revision.
**Status:** OPEN

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
