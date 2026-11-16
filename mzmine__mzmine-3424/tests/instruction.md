# Issue

**Title:** Volcano plot improvements

## Description

- if there were samples loaded but not in the feature list sometimes the plot would not update or load at all
- limit to featureList.getRawDataFiles
- Clear plot if update started
- show message with warnings if wrong metadata selected

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `59d40c28255d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.