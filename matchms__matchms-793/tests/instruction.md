# Issue

**Title:** Fix/tests for embedding similarities

## Description

This will fix tests for EmbeddingSimilarities:

- remove BaseEmbeddingSimilarity from [similarities\__init__.py](https://github.com/matchms/matchms/blob/master/matchms/similarity/__init__.py) (unsure, if that should be directly instantiated. Having it in init will fail test_scores_read_write)
- Skip asymmetrical score tests for BinnedEmbeddingSimilarity, since must be symmetrical
- Add tests for BaseEmbeddingSimilarity

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ff53f9d3829a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.