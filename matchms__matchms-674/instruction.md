# Issue

**Title:** Add require correct ms level 2

## Description

Saving incrementally resulted in a significant reduction of speed, when I tested it. From 50 spectra/s to 3 spectra/s.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6e5bcc725aef`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.