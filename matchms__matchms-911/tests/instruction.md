# Issue

**Title:** Refactor Cosine and ModifiedCosine wrapper

## Description

Internally those two methods now use:
- CosineGreedy / ModifiedCosineGreedy for the `.pair()` method
- CosineFlash for the `.matrix()` method. 

Those methods should hence be consistent!
This required two changes:
1. The CosineFlash default for `normalize_to_half` was now changed to False
2. By default, CosineGreedy / ModifiedCosineGreedy do now also run a basic noise filter (can be switched off). **This might change some past results slightly!**

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `af19a089ccdf`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.