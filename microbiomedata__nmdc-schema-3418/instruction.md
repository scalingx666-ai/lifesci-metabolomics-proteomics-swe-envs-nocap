# Issue

**Title:** Refresh the lock so transitive packages stop drifting behind

## Description

Dependabot keeps the lock current only for packages named in `pyproject.toml`: its last four Python pull requests bumped 2, 3, 4 and 3 declared packages and no transitive-only ones. So transitive packages drift behind, and a fresh `poetry install` after a `poetry update` shows dozens of downgrades. This refreshes the whole lock inside the existing constraints. Nothing in `pyproject.toml` changes.

## What changed

`poetry update --lock` changed 66 packages, added `httpcore2`, `httpx2`, `httpx2-jsfetch`, `opentelemetry-api` and `truststore`, and removed `distro`, `httpcore`, `httpx` and `pyopenssl`. Only 4 of the 66 are declared in `pyproject.toml`, all patch bumps: `curies` 0.15.0 to 0.15.1, `pandas` 3.0.3 to 3.0.5, `psycopg2-binary` 2.9.12 to 2.9.13, `pymongo` 4.18.0 to 4.18.1, plus `ruff` 0.16.6 to 0.16.7. Three transitive packages cross a major version: `backrefs` 7 to 8, `isort` 8 to 9, and `openai` 2.53.0 to 3.14.0.

## Validation

Run on 2026-09-15 with Poetry 2.4.3 and Python 3.13 on `main` at d41ef9577: `make squeaky-clean && make mixs-yaml-clean && make squeaky-clean && make src/schema/mixs.yaml && make squeaky-clean all test linkml-lint` exited 0, with 95 tests passed and no errors in the log. The regenerated `nmdc_schema/` files are not committed, per `CLAUDE.md`.

Rebuilding also reorders about 55 blocks in `src/schema/mixs.yaml` and collapses two double spaces in `root_med_macronutr` and `root_med_micronutr` examples, which happens on `main` too and has nothing to do with this lock. That file is left as committed here, and the drift is worth its own issue.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d41ef9577a33`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.