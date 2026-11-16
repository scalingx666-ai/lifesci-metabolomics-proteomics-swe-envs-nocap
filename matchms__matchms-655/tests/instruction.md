# Issue

**Title:** Fail fast on loading missing mgf

## Description

This is my proposed way of addressing #652 . Since generators do not run any code until we `list(...)` them, it's only possible to `raise` anything if we make the generator code a wrapped function. If anyone has a more elegant solution, I'm all ears :D 

Also added a test-case for this.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `abd7410f5921`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.