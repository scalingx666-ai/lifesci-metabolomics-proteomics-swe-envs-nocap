# Issue

**Title:** Make downsampling of training genes deterministic

## Description

The keys in a hash are not ordered. In some versions of Perl, the order of keys is consistent between runs but this is not guaranteed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `175279ae45f9`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.