# Issue

**Title:** Stabilize training

## Description

BRAKER training is sensitive to the order in which training genes appear on input. In other words, using two identical training gene sets may result in different final results if the order of training genes differs. This problem also occurs when the order of training genes is the same but their gene ids are formatted in a different way.

This update fixes this undesired behavior by sorting training genes and reassigning their ids prior to AUGUSTUS training.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `25513dacb291`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.