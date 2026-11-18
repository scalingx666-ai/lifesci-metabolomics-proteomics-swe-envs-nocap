# Issue

**Title:** Allow version 3.x of the `deprecated` dependency

## Description

## Why

Closes  Our `<2.0.0` cap was the only thing keeping deprecated 3.0.0 out of consumers' environments, and per  a library should keep its specifiers loose. I ran `poetry update --lock deprecated` so CI on Python 3.13 exercises 3.0.0; Python 3.10 and 3.11 stay on 1.3.1, because 3.0.0 needs 3.12 or newer.

## Validation

On Python 3.13 with deprecated 3.0.0 installed: `poetry check --lock` reports "All set!", `pytest tests/` passes (431), and calling `validate_nmdc_json.get_nmdc_schema()` still returns the schema dict and emits its `DeprecationWarning`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5c5947fe487a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.