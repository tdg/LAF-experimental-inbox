# DECISIONS-INBOX

Live queue of cross-cutting decisions awaiting LAF-00 parent resolution. See `README.md` for conventions.

**Last updated:** 2026-05-02 LAF-00.12
**Next parent session:** LAF-00.13 (TBD)

---

## Resolved this session (LAF-00.12) — kept visible for one session as audit trail

### DQ-STRAT-22 — Council vs ward as primary deliverable
**Raised:** 2026-05-01 LAF-03.01 (surfaced via post-LAF-00.11 side-note)
**Trigger:** Live SRUK site renders OG images at council level (`/local/{council}/`), not ward level. Ward-level LAF-01 sourcing was producing assets the live site couldn't directly consume.
**Scope impact:** LAF-01, LAF-03, LAF-04, LAF-05, LAF-06
**Status:** RESOLVED
**Resolution:** Council-level is primary deliverable. Ward-level demoted to "bespoke on demand" — generated for big urban councils where one image is meaningless, high-stakes wards Becky/Tom flag, or post-launch reactive content. Ward Wave 1 sourcing continues as input library for council-level selection. (LAF-00.12)

### DQ-STRAT-21 — Codebase migration to Git
**Raised:** ~2026-04-21 (Tom open intent), reraised 2026-05-01
**Trigger:** Project files in `/mnt/project/` are read-only from Claude's side; manual paste-back at every session boundary; no version control on Part A/B.
**Scope impact:** All workstreams (operating model)
**Status:** RESOLVED IN PRINCIPLE
**Resolution:** Promoted from "open intent" to "planned, post-7-May." Scope draft to follow post-election. Part B §19 to be updated. (LAF-00.12)

---

## Open items

### DQ-IMG-23 — Old Warley council attribution mismatch
**Raised:** 2026-05-02 LAF-01.08
**Trigger:** Brief documentation said Walsall, manifest + GSS confirmed Sandwell. Sourcer followed GSS as authoritative.
**Scope impact:** LAF-01 manifest provenance
**Provisional assumption:** GSS is authoritative; brief was wrong. Image and manifest reflect Sandwell.
**Decision needed by:** Non-blocking — confirm at next LAF-00.
**Status:** OPEN

### DQ-IMG-28 — Image storage migration & live-upload pattern
**Raised:** 2026-05-01 (post-LAF-00.11 side-note)
**Trigger:** Local outputs require laptop to stay on for downstream consumers (LAF-03 OG, future website). Need cloud-accessible store with concurrent upload pattern.
**Scope impact:** LAF-01, LAF-03, LAF-06
**Provisional assumption:** Wave 1 continues writing to local `~/dev/laf-01-02/outputs/`. Don't delete or move outputs directory until storage decision made.
**Decision needed by:** Non-blocking pre-polling. Adam Hodgkin to advise on backend (R2 vs B2 vs GitHub LFS) given SRUK fetch path.
**Status:** OPEN
**Notes:** Council pivot (DQ-STRAT-22) shrinks scope significantly: ~370 council images at ~75MB total, not 15,000 ward images at ~3GB. Adam conversation should reflect smaller storage problem.

### DQ-STRAT-23 — LAF filename convention (raised by Claude Code)
**Raised:** 2026-05-01 LAF-03.01 close-of-session
**Trigger:** Claude Code session noted inconsistencies in LAF filename convention application; details in close-of-session report on Tom's Desktop.
**Scope impact:** All workstreams (operating model)
**Provisional assumption:** Existing convention `LAF-NN.SS-[workstream]-[description].ext` continues until reviewed.
**Decision needed by:** Non-blocking — review when close-of-session report content is brought into project files.
**Status:** OPEN
**Notes:** Original CC numbering was DQ-STRAT-21, renumbered to DQ-STRAT-23 here to avoid collision with the codebase-migration item.

### DQ-VID-01 — Sound for video pipeline
**Raised:** 2026-05-02 LAF-00.12
**Trigger:** Video sound was open from LAF-04.01; surfaces again ahead of LAF-04.02. Editor needs sound options alongside image options at edit time.
**Scope impact:** LAF-04
**Provisional assumption:** Sound becomes sub-child of LAF-04; editor matches sound to vision creatively (potentially surprisingly), not literally to geography.
**Decision needed by:** Before LAF-04.02 council paper-edit pass.
**Status:** OPEN
**Action item:** LAF-00.12 to produce CC-licensed shortlist (3 ambient/soundscape: industry + nature; 3 music tracks varying moods; silent track; local-upcoming-band angle if findable) plus topline scoping summary for CC sound use.

### DQ-PROCESS-01 — Surface upstream-scope-changing facts from child sessions immediately
**Raised:** 2026-05-02 LAF-00.12
**Trigger:** DQ-STRAT-22 (council pivot) was discovered by LAF-03.01 child session but not surfaced to parent for ~2 weeks; sat as in-session implementation note.
**Scope impact:** Operating model (Part B)
**Provisional assumption:** Cross-cutting facts from execution sessions go into this inbox (DECISIONS-INBOX.md) on discovery, not at session close.
**Decision needed by:** Adopt at LAF-00.12 close.
**Status:** OPEN
**Notes:** This inbox repo *is* the resolution mechanism — DQ-PROCESS-01's resolution will likely be "adopted, see Part B v4.7."

### DQ-DATA-01 — D4D recommendations for Senedd constituencies
**Raised:** 2026-05-02 LAF-00.12
**Trigger:** Wales 2026 = 16 closed-list PR constituencies (D'Hondt), not council elections. Tactical-vote logic differs from FPTP councils. Need to confirm what recommendations D4D holds for Senedd constituencies and how they're shaped.
**Scope impact:** LAF-01.09, LAF-04, LAF-05
**Provisional assumption:** LAF-01.09 doesn't fire for Wales until D4D check completed.
**Decision needed by:** Before LAF-01.09 fires.
**Status:** OPEN

### DQ-DATA-02 — D4D recommendations for Scottish AMS regions
**Raised:** 2026-05-02 LAF-00.12
**Trigger:** Scotland 2026 = Scottish Parliament elections (AMS). SNP competitive across most 73 FPTP constituencies (progressive party — sparse recommendations expected). Regional list (8 regions) is where pluralism leverage exists.
**Scope impact:** LAF-01.09, LAF-04, LAF-05
**Provisional assumption:** LAF-01.09 Scotland scope = 8 AMS regions. Constituencies and council areas out of scope.
**Decision needed by:** Before LAF-01.09 fires.
**Status:** OPEN

### DQ-OG-01 — Reframe OG Issue: Phase 1 council swap, Phase 2 ward future scope
**Raised:** 2026-05-02 LAF-00.12 (from CC handoff)
**Trigger:** Issue body drafted 2026-05-01 with ward-level framing; council pivot taken at LAF-00.12 makes ward framing stale.
**Scope impact:** LAF-03
**Provisional assumption:** Reframe required before posting. Remote agent armed for Sun 3 May 20:00 UTC reports "not posted yet" if Issue isn't up — harmless if reframe slips past Sunday.
**Decision needed by:** Sun 3 May 20:00 UTC if posting this weekend, otherwise can slip to post-polling.
**Status:** OPEN (action taken in LAF-03.02; awaiting Becky review + Tom post)
**Action item:** LAF-00.12 produces kickoff brief for CC follow-up session: reframe Issue body + rebuild Adur OG comparison image (Lancing Ring as council-level swap). Becky review before post.
**Update 2026-05-03 LAF-03.02:** Reframe complete. Issue body + Adur/Lancing Ring mockup produced at `~/Desktop/LAF-00-12-Strategy/LAF-03_02-og-issue-council-phase1.md` and `~/Desktop/LAF-00-12-Strategy/LAF-03_02-og-adur-lancing-ring-mockup.png`. Phase 1 framed as ~150 council bg swaps (~30MB total in-repo); Phase 2 ward-level demoted to future Issue with Cokeham mockup preserved at `~/Desktop/LAF-00-11-Strategy/LAF-03_01-og-cokeham-comparison.png` for that future use. Status closes to RESOLVED on Issue post.

### DQ-OG-02 — Council count precision (LAF-05 dependency)
**Raised:** 2026-05-03 LAF-03.02
**Trigger:** LAF-03.02 Issue body uses "~150 English councils with elections" as a working estimate. The grounded subset from in-flight Wave 1 is 84 councils / 1,004 wards. LAF-05 (D4D) has not yet produced a clean ballot-list-derived council count for May 2026 cycle.
**Scope impact:** LAF-03 (Issue copy precision), LAF-05 (manifest)
**Provisional assumption:** "~150" stated in Issue; precise figure not load-bearing for the proposal.
**Decision needed by:** Non-blocking. Precise figure helpful before any final Phase 1 manifest curation; surface to LAF-05 if blocking.
**Status:** OPEN

### DQ-OG-03 — Current OG generation mechanism unknown
**Raised:** 2026-05-03 LAF-03.02
**Trigger:** Live SRUK serves `/local/{council}/og.png` as a 1200×630 PNG. We don't know whether it's a static asset bundled in `/public/local/{council}/` at build time, or generated dynamically (e.g. via `@vercel/og`). Asked the maintainer in Issue Open question 1.
**Scope impact:** LAF-03 (PR scope for Phase 1)
**Provisional assumption:** Issue describes the requirement bg-source-agnostic; PR scope decided by maintainer's answer.
**Decision needed by:** When Phase 1 PR is scoped (LAF-03.03 follow-up).
**Status:** OPEN

### DQ-OG-04 — Mockup wordmark recreation is schematic
**Raised:** 2026-05-03 LAF-03.02
**Trigger:** Adur Lancing Ring mockup recreates the StopReformUK wordmark with Helvetica `StopReformUK` text + Unicode `✗` glyph in FD pink, rather than compositing the real X-stroke + brush-mask brand assets (`brandlogoxshape.png` etc). Functional for showing a bg swap, but not pixel-faithful to the real OG.
**Scope impact:** LAF-03 (mockup quality)
**Provisional assumption:** Ship mockup as-is; flagged in Issue body as schematic.
**Decision needed by:** If maintainer requests pixel-faithful comparison, re-render mockup with real brand assets composited (LAF-04 video template knows how).
**Status:** OPEN

### DQ-OG-05 — Polling-day count drift in LAF-03.02 kickoff brief
**Raised:** 2026-05-03 LAF-03.02
**Trigger:** LAF-03.02 kickoff stated "Polling day: Thu 7 May 2026 (5 days)" but today is Sun 3 May 2026 — 4 days, not 5. Trivial off-by-one in brief authoring.
**Scope impact:** Operating model (parent brief-template review only)
**Provisional assumption:** Used 4 in close-of-session and Issue copy; no downstream impact.
**Decision needed by:** Whenever — folded into parent's template review.
**Status:** OPEN

---

## Action items (LAF-00.12)

These are not DQs but explicit work items emerging from this session:

- [ ] Produce CC-licensed sound shortlist + scoping summary (DQ-VID-01)
- [ ] Updated LAF-01.09 kickoff brief: 8 Scotland AMS regions + 16 Wales Senedd constituencies (subject to DQ-DATA-01/02)
- [ ] Updated LAF-04.02 kickoff brief: small ward batch + council paper-edit format (6–8 wards/frame) + sound DQ
- [ ] Kickoff brief for CC follow-up: reframe OG Issue (DQ-OG-01)
- [ ] Updated Part A v4.10 + Part B v4.7
- [ ] Slice 4 go-message back to image session (ENG remainder, halt at end, do not start LAF-01.09)

---
