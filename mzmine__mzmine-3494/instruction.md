# Issue

**Title:** NPE in GC networking when NIST spectral match present

## Description

- GC networking when NIST spectral match has overlapping signals null hits NPE - .overlap is safe

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `080180794212`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.