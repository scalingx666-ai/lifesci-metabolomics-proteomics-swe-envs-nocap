# Issue

**Title:** [performance]: better isotope utils

## Description

Fixes two small issues:

- Google Range() is not suited for usage in hot-path of the code, i.e. when iterating over huge lists. Complexity of the self-rolled solution is also low. This should bring a ~30% Performance improvement.

- JSONReader creation causes a full classscan on each factory initialization,

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f0a1a8301ba0`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.