# Issue

**Title:** Updated matchms dependencies

## Description

This PR updates the matchms dependencies.

python = ">=3.9,<3.13" -> python = ">=3.10,<3.13"
numpy = ">1.22, <1.27" -> numpy = "^2.0"
scipy = ">=1.11" -> scipy = "^1.14.1"
pandas = ">=2.0.3" -> pandas = "^2.2.3"
networkx = ">=3.0" -> networkx = "^3.4.2"
numba = ">=0.57.1,<0.60" -> numba = "^0.60.0"
sparsestack = ">=0.4.1" -> sparsestack = "^0.6.0"

Especially updating the deps of numpy, scipy, numba and pandas will make a big difference.

This 

This will also help with https://github.com/iomega/spec2vec

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `4e1cbaf06cec`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.