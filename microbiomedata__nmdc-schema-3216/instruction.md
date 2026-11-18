# Issue

**Title:** Add no-op migrators for the 11.20.x patch series

## Description

The migrator chain stops at `migrator_from_11_19_1_to_11_20_0`. The 11.20.1 and 11.20.2 releases shipped schema changes without migrators, so the chain is broken across the 11.20.x patch series. This adds the three missing no-op migrators (11.20.0 to 11.20.1, 11.20.1 to 11.20.2, 11.20.2 to 11.20.3) to restore continuity, including the one needed for the upcoming 11.20.3 release.

All three increments are additive: new slots, new enums, new optional slots on LibraryPreparation, and one DataObject rule whose precondition is a new data_object_type value. No constraint on an already-released slot was tightened (checked added and removed constraint lines across all three diffs), so no data valid under the earlier schema becomes invalid. That is why each migrator is a no-op.

cc: @eecavanna

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `68bcdee15ad1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.