# Issue

**Title:** fix overlap in SimpleDoubleRangeMap

## Description

Addition of a new range checked if the edges of the proposed range were included in another range. in rare cases, this may have enclosed another range. in the guava implementation these ranges were swallowed, this implementation now check the closed ranges to the center point of the new range

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d01c53215132`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.