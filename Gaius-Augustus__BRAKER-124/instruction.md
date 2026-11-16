# Issue

**Title:** braker.pl : Fix key in ES gene length computation

## Description

Value in $1 variable was being overwritten by a subsequent regex search for CDS
(related to issue )

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `cf2dd4a1125f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.