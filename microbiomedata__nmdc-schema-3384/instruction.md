# Issue

**Title:** Make `name` required on `PersonValue` and implement migrator

## Description

.

**Schema changes**
- Made `name` required on `PersonValue` class

**Migrator**
- From schema `11.23.0` to `11.24.0`.
- `study_set` and `data_generation_set`: normalize `name` on each of the values in the `has_credit_associations` by filling in from `has_raw_value` as needed and after whitespace stripping.  Raises error if it cannot be filled from `has_raw_value`. Migrator is `nmdc_schema/migrators/partials/migrator_from_11_23_0_to_11_24_0/migrator_from_11_23_0_to_11_24_0_part_3.py`
- migrator was tested locally against production mongo data using `make test-migrator-on-database MIGRATOR=migrator_from_11_23_0_to_11_24_0 SELECTED_COLLECTIONS=study_set` and `make test-migrator-on-database MIGRATOR=migrator_from_11_23_0_to_11_24_0 SELECTED_COLLECTIONS=data_generation_set` with no issues found

**Example Data**
- Added `name` slot on all `PersonValue` instances in `src/data/valid/` (several locations)
- Added `src/data/invalid/PersonValue-missing-name.yaml`: fails only because `name` is not present

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c068568bbeaa`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.