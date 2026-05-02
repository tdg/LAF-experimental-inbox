# LAF-experimental-inbox

Single source of truth for cross-cutting decisions across the **Local Asset Factory (LAF)** project — Forward Democracy's ward-and-council-level campaign content pipeline for the May 2026 local elections.

## Why this repo exists

LAF runs as a parent strategy session (`LAF-00.NN`) coordinating multiple parallel execution workstreams:

- **LAF-01** Images
- **LAF-02** Static social cards
- **LAF-03** OG images for StopReformUK.vote
- **LAF-04** Video
- **LAF-05** Data (D4D queries and manifests)
- **LAF-06** Distribution

When a child execution session encounters a fact that changes upstream scope, or needs a parent-level decision, it appends to **`DECISIONS-INBOX.md`** in this repo rather than holding it in a session-local DQ list. Parent strategy sessions (`LAF-00.NN`) read the inbox at session open and resolve items at session close.

## Files

| File | Purpose |
|---|---|
| `DECISIONS-INBOX.md` | Live queue of cross-cutting decisions awaiting parent resolution. Cleared progressively at each LAF-00 close. |
| `README.md` | This file. |

## Conventions

### Identifiers

Each item carries a `DQ-[CATEGORY]-[N]` identifier. Categories in current use:

- `STRAT` — strategy / project-shape decisions
- `IMG` — image workstream
- `VID` — video workstream
- `OG` — OG-image workstream
- `DATA` — D4D / manifest decisions
- `PROCESS` — operating-model / convention changes

Numbering is monotonically increasing within category. Don't reuse numbers even after items are resolved and removed.

### Item structure

```markdown
## DQ-[CATEGORY]-[N] — [short title]
**Raised:** [YYYY-MM-DD] [session ID, e.g. LAF-03.01]
**Trigger:** [one sentence — what surfaced this?]
**Scope impact:** [which workstreams affected]
**Provisional assumption:** [what the child is assuming while waiting; "blocking" if work halts]
**Decision needed by:** [date / "blocking" / "non-blocking"]
**Status:** OPEN | RESOLVED | SUPERSEDED
**Resolution (if resolved):** [one-line outcome + LAF-00 session reference]
```

### Workflow

1. **Child session encounters cross-cutting fact.** Appends new item to `DECISIONS-INBOX.md` with `Status: OPEN`. Single git commit. Continues work under the stated provisional assumption.
2. **Parent (LAF-00.NN) opens session.** Reads inbox first. Each `OPEN` item is either resolved during the session or carried forward.
3. **Parent close-of-session.** Items resolved this session move to `Status: RESOLVED` with a one-line resolution note. The full resolution detail goes into the parent's Part A decision history. Resolved items are kept in the inbox for one session as a visible audit trail, then removed at the *next* session open (so each LAF-00 always sees the immediately prior resolutions).

### Time handling

All dates UK time. Polling day is **Thursday 7 May 2026**. Pre-polling work is the highest-priority decision-driver in this inbox.

## Access

Public read. Tom commits via GitHub web UI or `git push` from local. Claude Code execution sessions can read/write directly via `git`. Claude.ai sessions read via `web_fetch` of `https://raw.githubusercontent.com/tdg/LAF-experimental-inbox/main/DECISIONS-INBOX.md` and produce drop-in replacements for Tom to commit.

## Status

This repo is **experimental** — set up 2 May 2026 to replace the previous "drop-in-replacement Part A/B" pattern, which had a silent-overwrite failure mode under parallel sessions. If the pattern works through polling day, it'll be folded into the broader codebase migration planned post-7-May.
