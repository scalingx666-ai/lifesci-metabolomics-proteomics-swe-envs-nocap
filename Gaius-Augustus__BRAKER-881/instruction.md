# Issue

**Title:** fix for using other openjdk java (e.g. Zulu from Azul)

## Description

We are using openjdk from azul (zulu). In order to make braker.pl work, the attached patch had to be applied. 
It still works with standard openjdk java.

Please consider merging this

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `35280d0c2f56`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.