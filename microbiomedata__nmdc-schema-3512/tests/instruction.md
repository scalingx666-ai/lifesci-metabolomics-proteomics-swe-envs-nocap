# Issue

**Title:** Add doctests for LinkML 1.12 wrapped id patterns

## Description

## Why

 made `get_compatible_typecodes` accept the `^(?:...)$` wrapping that linkml-runtime 1.12 adds to id patterns. Our lock still installs linkml-runtime 1.11.1, so CI never sees a wrapped pattern and a regression in that regex would pass CI. Users who `pip install nmdc-schema` already get 1.12.x.

These doctests give the wrapped form fixed inputs, so `make test` (which runs `python -m doctest nmdc_schema/id_helpers.py`) checks it under any linkml version.

## Validation

All 21 doctests in `nmdc_schema/id_helpers.py` pass with linkml and linkml-runtime 1.11.1 and with 1.12.1. With the regex from before  the three new examples fail.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `73fa931aa656`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.