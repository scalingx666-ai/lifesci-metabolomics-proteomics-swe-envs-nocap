# Issue

**Title:** Fixed modified cosine behavior for precursor deltas within tolerance

## Description

This PR fixes issue #866 where `ModifiedCosineGreedy` and `ModifiedCosineHungarian` could behave differently from regular cosine even when precursor m/z differences were within tolerance (including boundary cases). We now compute the precursor shift once and, when `|precursor_mz_ref - precursor_mz_query| <= tolerance`, delegate directly to `CosineGreedy`/`CosineHungarian` so behavior is consistent with the expected unshifted case; dedicated tests were added for zero, positive-boundary, and negative-boundary deltas to confirm parity.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b835bbb1c79d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.