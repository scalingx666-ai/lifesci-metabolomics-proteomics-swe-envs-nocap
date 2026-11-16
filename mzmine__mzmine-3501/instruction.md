# Issue

**Title:** add SimpleFloatRange + migrate Gap.java to use it

## Description

faster version of Guavas Range, analogous to the existing SimpleDoubleRange/SimpleIntegerRange implementations.

Avoids boxing/unboxing and allows more jitting/inlining magic.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `080180794212`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.