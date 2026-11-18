# Issue

**Title:** Objectify the Biosample slot_usage examples in core.yaml

## Description

## Why

Twelve `Biosample` `slot_usage` overrides in `src/schema/core.yaml` still carried scalar `value:` examples for slots whose range is a wrapper class (`QuantityValue`, `TextValue`). Two consequences: the example does not have the shape a real instance has, and because an override shadows the slot underneath it, these twelve were hiding the objectified MIxS examples the rest of the stack produces. They are the only remaining failures of `test_example_form_matches_range`.

## What

Each scalar becomes an object of the slot's range, with the original string preserved verbatim in `has_raw_value`. Nothing was dropped. These overrides exist because they carry NMDC-specific values, and those all survive: the second `gaseous_environment` regimen, the multi-metal `heavy_metals` string, the preferred `ph_meth` citations, and the igsn and UUID forms of `source_mat_id`.

`test_example_form_matches_range` moves here from  It was written there but fails there, because the change that satisfies it is this one. Each PR is now green on its own.

Based on `examples-integration` rather than `main`, because the test only reaches these twelve once the rest of the stack has objectified everything else.

## One thing to check

`slope_gradient` had three examples: `10%`, `10 %`, and `0.10`. Its todo ("Slope is a percent. How does the validation work? Check to correct examples") suggests they were there to probe whether all three forms would validate, not to record three different measurements. I wrote `0.10` as the dimensionless fraction it reads as, `has_numeric_value: 0.10` with `has_unit: "1"`. If the intent was that `0.10` means the same quantity as `10%`, it should instead be `has_numeric_value: 10` with `has_unit: "%"`, or dropped as redundant. Your call.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f2ef34d9ee6f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.