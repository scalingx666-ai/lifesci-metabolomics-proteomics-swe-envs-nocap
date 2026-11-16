# Issue

**Title:** within set_JAVA_PATH, generalize check for java version and prevent substitutions within awk command

## Description

Within `set_JAVA_PATH`, generalizes the check for java version to `grep` just for `version` (e.g., our system java is not OpenJDK) and fences off the awk command within single quotes to prevent substitution of the contained `$2,$3` with empty values that occurred because the surrounding context was double quotes.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `00f1c2ec896c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.