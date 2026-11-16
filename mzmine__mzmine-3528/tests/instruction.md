# Issue

**Title:** Theme fixes

## Description

- fix almost no contrast in themes between button background and font in dialogs (e.g. mzmine close)
- fix renderer label font color not applied -> black font in dark mode

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `968de4e1ac5a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.