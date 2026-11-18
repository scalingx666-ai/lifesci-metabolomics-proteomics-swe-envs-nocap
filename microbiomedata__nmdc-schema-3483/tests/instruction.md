# Issue

**Title:** Add interpolated: true to three id structured patterns

## Description

## Why

Closes  Three `id` structured patterns omitted `interpolated: true`. linkml 1.11 expanded them anyway; linkml 1.12.0rc2 leaves them as literal `{id_nmdc_prefix}` text, so example validation fails once we move to 1.12. The new test, `tests/test_structured_patterns_interpolated.py`, fails whenever a pattern with `{...}` placeholders omits the flag, so this can't come back unnoticed.

## Validation

- On linkml 1.11.1, `make squeaky-clean all test` passes (432 tests). The regenerated artifacts differ from `main` only by the added `interpolated: true` metadata; every expanded id pattern is identical. Per CLAUDE.md, the generated files are not committed here.
- On linkml 1.12.0rc2 with this change, all 431 Python tests on `main` pass, where `test_all_valid_examples` failed before. (The build still fails a doctest for a separate reason, tracked in )
- With the schema change reverted, the new test fails and names exactly the three patterns.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5c5947fe487a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.