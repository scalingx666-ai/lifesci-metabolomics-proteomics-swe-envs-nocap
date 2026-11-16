# Issue

**Title:** batch-order: relax mass detection condition

## Description

Before this fix, rules with MassDetectioCondition.MSany would show a warning if there was no single mass detection applied to all ms levels.

This means mobility scan merging or ftms shoulder peak filter would require a mass detection to all scans in all ms levels. usually, different ms levels require different noise levels. so this condition now succeeds if there is a mass detection step.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `941c7ed269e3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.