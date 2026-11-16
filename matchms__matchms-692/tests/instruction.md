# Issue

**Title:** Numpy replace njitted

## Description

PR from @tornikeo #638 
> Addressing  I rewrote the njitted functions using plain matmul operations, using numpy. This [is around x50 times faster](https://colab.research.google.com/drive/1dYvdcbkUUOubgjPAZTtsfpG5Z7duc1kw?usp=sharing) (2s for 1k pairwise 1k peaks, vs 40ms).

I only added some minor linting. And a (totally unrelated) addition of a missing docstring to make SonarCloud happy.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a038e0b3873a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.