# Issue

**Title:** Adding instructions to compile the conda package

## Description

This PR includes a new directory,  `devtools`, with the instructions and files needed to compile and upload pypdb as a conda package. The README file in `devtools/conda-recipe/` was written with some indications assuming there is a conda channel called "williamgilpin".

I forked your repository to have it available in the conda channel of our lab: see [this](https://anaconda.org/uibcdf/pypdb). And I thought that this could be shared with you, maybe you want to have your own conda channel with pypdb.

If you are not interested, just decline the PR. No problem.
Thanks for developing PyPDB!

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0e75a05dda24`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.