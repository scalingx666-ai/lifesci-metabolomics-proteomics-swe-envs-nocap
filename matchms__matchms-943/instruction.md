# Issue

**Title:** Consistent offset renaming and logic

## Description

Rename `precursor_window` parameter to `offset_to_precursor` (because it actually is not applied in form of a "window"), and make the logic consistent with the `remove_peaks_relative_to_precursor` filter function. This also includes setting the default offset to `-1.6Da`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `190fea2509ca`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.