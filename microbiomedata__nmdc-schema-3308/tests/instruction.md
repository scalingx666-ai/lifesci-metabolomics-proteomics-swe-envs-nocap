# Issue

**Title:** Create "no op" migrator between versions 11.21.0 and 11.22.0

## Description

On this branch, I created a routine "no op" migrator for a schema jump that requires no data migration.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c91ae23e228`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.