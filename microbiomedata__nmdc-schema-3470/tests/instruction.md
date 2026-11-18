# Issue

**Title:** Finalize deprecation of `collection_time_inc`

## Description

(the second half)

This PR finalizes the deprecation started last release of `collection_date_inc`. 
See  for related discussions as well.

This PR is to be merged along with  so that deprecation occurs in the submission schema and the nmdc schema simultaneously.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `647010882b23`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.