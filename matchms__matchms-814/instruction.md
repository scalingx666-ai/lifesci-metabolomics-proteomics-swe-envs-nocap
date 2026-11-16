# Issue

**Title:** Fixed metadata export

## Description

Somehow this slipped away, the metadata export function didn't work, I changed some of the assigned datatypes in the array and fixed the tests. Also, the keys now get sorted, so that the returned array should be always the same

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `fe3a8b393e4a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.