# Issue

**Title:** Add a migrator check that fails on `collection_time_inc`

## Description

Closes  (Add a migrator check that fails on `collection_time_inc` before the next release).

 removed `collection_time_inc` from `Biosample`, so a database that is valid under 11.24.1 may not be valid under the next release. A migrator is needed even though production has no such records (checked 2026-10-07 and 2026-10-08).

This adds `migrator_from_11_24_1_to_11_25_0` with one partial. The partial raises if any `biosample_set` document has the slot and changes nothing otherwise. It doesn't drop the value, because the replacement depends on what the value meant: the harvested sample's `collection_time`, or the dates of a processing step. It follows the same pattern as `migrator_from_11_10_0_to_11_11_0_part_1.py`, and the removed slots are in a list that  can extend.

I assumed the next release is 11.25.0. If it gets a different number, the file names and `_to_version` values need to change.

## Validation

- `python -m doctest` on the new files: 9 examples pass, including one with the slot that raises and one with an empty value that also raises.
- `python -m doctest nmdc_schema/migrators/*.py` passes, so existing migrators are unaffected.
- I didn't run the full `make test` locally. CI runs it.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1c70a442ac5b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.