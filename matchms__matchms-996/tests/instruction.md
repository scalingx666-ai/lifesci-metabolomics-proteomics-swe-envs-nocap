# Issue

**Title:** Remove dev-requirements as manifest from dependabot

## Description

Exclude dev-requirements.txt as manifest from dependabot to use uv.lock as single source of truth.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `acfd555983df`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.