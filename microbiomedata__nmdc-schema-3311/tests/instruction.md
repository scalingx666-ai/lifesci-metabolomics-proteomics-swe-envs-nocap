# Issue

**Title:** Drop the dimensionless placeholder unit from two has_raw_values

## Description

Part of

`carb_nitro_ratio` and `occup_samp` carried `has_raw_value: "20.6 1"` and `"10 1"`. `1` is the UCUM placeholder for dimensionless, not something a submitter would ever type into that field, and upstream MIxS writes both examples bare (`'0.417361111'`, `'10'`). Introduced by 5c5185f03, which built `has_raw_value` as numeric plus unit; right for a real unit, wrong for the placeholder.

These two are the unblocked half of issue 3310. Their `storage_units` already agrees with `has_unit`, so there is no modeling question to settle first.

The other three (`iwf`, `rel_air_humidity`, `surf_humidity`) are deliberately untouched. They assert `storage_units: "%"` against `has_unit: "1"`, so dropping the suffix alone would leave `0.8` on a slot documented as percent. Those wait on  and 3310 stays open tracking them.

`src/schema/mixs.yaml` was updated by running the two edited customization lines through `eval yq` under bash, which is what `makefiles/mixs.Makefile` does, rather than by a full regeneration. 71 tests pass.

Surfaced while building submission-schema against `11.23.0rc1`, where the malformed raw values on the contested three break `test_examples`.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f1e24ec0b4b2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.