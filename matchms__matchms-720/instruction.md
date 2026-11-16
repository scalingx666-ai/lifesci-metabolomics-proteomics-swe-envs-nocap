# Issue

**Title:** Add ecosystem dependency tests

## Description

This should fix #718.
This adds a workflow to test compatibility of some packages of the matchms ecosystem (spec2vec, ms2deepscore, ms2query and numpy 1.25/2.1). Workflow is triggered on `pull request` and on commit into `master`.

The results will be added as comment into the PR or update a section of the [README.rst](https://github.com/matchms/matchms/blob/add_ecosystem_dependency_tests/README.rst#ecosystem-compatibility)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5e92aeeef274`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.