# Issue

**Title:** Remove auto param from modules list, fix advanced param application

## Description

- Auto parameters is only used internally and the Ui is not nice, hence remove it from the menu. can be useful for debugging.
- Custom parameters were still applied even if the advanced mode was disabled

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c1a28f9c701`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.