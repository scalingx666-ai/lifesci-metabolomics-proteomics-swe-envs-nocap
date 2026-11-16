# Issue

**Title:** Update numba and numpy

## Description

- Allow numba up to `<0.60` and numpy up to `<1.27`.
(Helps because Pandas 2.0 requires numpy > 1.25)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1edd60157fb7`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.