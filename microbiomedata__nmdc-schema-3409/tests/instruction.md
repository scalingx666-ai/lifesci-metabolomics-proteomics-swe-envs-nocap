# Issue

**Title:** Quiet migration doctests by default and stop echoing MIxS customization lines

## Description

## Why

`make test` prints thousands of lines of passing doctest output, which buries anything that matters. The cause is recorded in  `DOCTEST_OPT` defaults to `-v`. A second source, named in  is the MIxS customization loop, which echoes every one of its lines on every rebuild.

Closes  Part of  which also proposes an opt-in `QUIET` toggle that this does not add.

## What changed

- `DOCTEST_OPT` now defaults to empty. `make migration-doctests DOCTEST_OPT=-v` restores the old output.
- The customization loop no longer echoes each line. If a line fails, it prints that line and stops, as before.

## Validation

Run in a worktree off `main` at 5307f144f, using the existing Poetry environment.

- `make migration-doctests`: exit 0 both ways. Output drops from 5,256 lines with `-v` to 137 by default. The verbose log shows 110 "Test passed." and no failures. The 137 lines left are the migrators' own INFO logging.
- Customization loop: Customization loop: on the same 922-line input, the old and new loops produce byte-identical files, and the real `make local/mixs_regen/mixs_subset_modified.yaml` target matches. The old loop printed 922 lines, the new one prints none. A deliberately broken line still exits 1 and prints `yq customization failed: '.slots.zz_bad |= ((('`.

## Documentation impact

The comment above `DOCTEST_OPT` now says how to get verbose output.

## Scope and complexity

Two Makefile recipes. No schema, data or dependency changes.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

https://claude.ai/code/session_01NDbXnpG2GdSN3Dq3sFuzPR

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5307f144ff1f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.