# Issue

**Title:** Pin poetry 2.5.1 everywhere and test that the pins agree

## Description

## Why

Closes  Poetry was pinned to 2.4.3 in ten places while the current release is 2.5.1, and Dependabot can't update versions written in `run:` steps. This moves every pin to 2.5.1 and adds `tests/test_poetry_version_pins.py`, which fails if the workflows, `Dockerfile` and `DEVELOPMENT.md` pin different versions.

Sharing one value across workflow files would need a repository variable (a settings change), so the test is the lighter way to keep them together.

## Validation

With poetry 2.5.1 on `main` (daa2253): `poetry check` and `poetry check --lock` report "All set!", and `poetry lock` leaves `poetry.lock` byte-identical. `make squeaky-clean all test` passes. The new test fails when one file is set back to 2.4.3.

Merge after the 11.24.1 release.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `8f0cd283ba37`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.