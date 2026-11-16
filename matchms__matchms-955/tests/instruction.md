# Issue

**Title:** Use float64 by default for BlinkCosine scores

## Description

BlinkCosine was the only similarity score returning float32, which led to mixed float dtypes when stacking scores in one Scores object. Scores are now computed and returned as float64 by default, consistent with the other cosine scores. A new `dtype` parameter (same pattern as FlashSimilarity) allows opting into float32 to reduce memory usage.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `622fcbb9578b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.