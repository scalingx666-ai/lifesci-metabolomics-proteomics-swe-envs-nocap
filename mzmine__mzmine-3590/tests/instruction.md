# Issue

**Title:** Record Community package version and source commit

## Description

Published Community JARs currently do not identify the source revision used to build them. Add `META-INF/mzmine/community-build.json` with the package version and Git commit so consumers can retain that information for traceability. No clean/dirty status is recorded; builds without Git record an unknown commit.

This change targets `feat/auto-mcp`. Source commits are informational and are not a Pro packaging acceptance gate.

Validation:
- Passed the isolated Gradle fixtures for resource/JAR inclusion, updated commits, unchanged metadata after working-tree edits, and builds without Git.
- Generated the metadata through the actual Community Gradle task.
- `git diff --check` passed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c17270f8900`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.