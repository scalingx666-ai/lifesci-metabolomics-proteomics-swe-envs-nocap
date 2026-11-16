# Issue

**Title:** Use `None` for unsuccessfully derived entries

## Description

Several filter functions added `""` entries when deriving was not possible, this was now changed to `None` entries, which properly represent missing entries in `SpectraCollection`. Addresses #951

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7fe817190973`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.