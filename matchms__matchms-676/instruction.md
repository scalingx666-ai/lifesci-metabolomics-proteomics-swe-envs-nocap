# Issue

**Title:** Add repair parent mass from smiles

## Description

Adds a filter to repair the parent mass from smiles
The parent mass is only repaired if it is not already close to the smiles monoisotopic mass.

Also moves all adduct/parent mass repairing filters after requires valid annotaion.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `822892a57737`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.