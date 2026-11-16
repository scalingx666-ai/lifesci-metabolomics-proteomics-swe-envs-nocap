# Issue

**Title:** add Docker image generation

## Description

Needs repository secrets:
- `DOCKERHUB_USERNAME`
- `DOCKERHUB_TOKEN`
- `DOCKERHUB_REPOSITORY` (name of repository to push image to)

The image will be tagged with a lowercase sirius_version, i.e. `5.7.0-snapshot`.

Example:
- `DOCKERHUB_USERNAME` = boecker-lab
- `DOCKERHUB_REPOSITORY` = sirius-docker

This would currently result in the image `boecker-lab/sirius-docker:5.7.0-snapshot`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3fdc83b0fefe`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.