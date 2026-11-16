# Issue

**Title:** Sort compound preferred row by ion type ranking

## Description

- this is not the default sorting but the secondary option for defining the representative compound row
- now uses: ion ranking, then AQS, then intensity 
- the default option uses: AQS first

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f5aea8e28a43`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.