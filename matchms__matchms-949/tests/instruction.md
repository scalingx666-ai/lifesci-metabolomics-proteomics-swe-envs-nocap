# Issue

**Title:** make pynndescent import lazy

## Description

Make `pynndescent` import lazy to allow faster `matchms` import (many people will not use that part of the library anyway).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `37b62f4f460e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.