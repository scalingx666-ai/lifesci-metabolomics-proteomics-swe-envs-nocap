# Issue

**Title:** Remove pandas usage and dependency.

## Description

pypdb depends on pandas which is a fairly big package for one minor use. This change allows to remove this dependency and while essentially keeping the same feature.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `386359f91c5e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.