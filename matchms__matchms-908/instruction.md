# Issue

**Title:** Merging master branch and adjust new code pieces

## Description

- merge newer additions from master branch
- most importantly: `LinearCosine` added by @LucaCappelletti94 (here adapted to the "new" matchms BaseSimilarity class)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1f9be264ab23`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.