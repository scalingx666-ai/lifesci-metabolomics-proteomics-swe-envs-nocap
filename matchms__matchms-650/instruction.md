# Issue

**Title:** Remove profile spectra

## Description

A method to remove likely wrongly converted profile spectra, by checking if there are multiple peaks surrounding the highest peak that have a high intensity.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a690961c0d60`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.