# Issue

**Title:** Adjust combined spectra hashes sha1 -> sha256

## Description

This fixes weak combined spectra hashing as marked as insecure by SonarQube.
Since we just use hashing as a identifier we could also use hashlibs flag `usedforsecurity=False`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d7dc8318cb49`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.