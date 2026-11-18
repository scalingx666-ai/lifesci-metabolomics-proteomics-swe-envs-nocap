# Issue

**Title:** Get the SIP branch green: regenerate mixs.yaml, objectify examples, repair the import TSV

## Description

Fixups on  targeting that branch so @aclum can take or leave them. Both of its failing "Build and test" jobs are green here.

Five changes are mine rather than @aclum's and need her agreement:

1. **`isotopolog` is constrained** on `LabelingProcess`: `has_raw_value` required, and `term.id` must be `PUBCHEM.COMPOUND:<CID>` with no CID 0. Nothing was enforced before, not even an empty object. This uses `range_expression`, new to this schema, so it ships with two valid and four invalid examples.
2. **`isotopolog_dose` becomes a `QuantityValue`** with `[ppm]`, matching the other SIP measurements.
3. **`gradient_pos_density` stores `g/cm3`.** `g/mL` is not a `UnitEnum` value, so that line could never have worked.
4. **`g/mL` is added as an alias** of `g/cm3`, which touches a shared enum.
5. **The `MIXS:0001345` mapping is removed.** @turbomam's call; it mapped a class to a slot.

One correction worth naming: both new classes had a `class_uri` local name that did not match the class name, which is what made the type designator reject the example data.

The rest is mechanical. Regenerating `mixs.yaml` so the three yq lines from 2f51c1418 take effect, 14 malformed rows in the import TSV, and example data that could not have validated.

Happy to give the reasoning behind any of these.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

https://claude.ai/code/session_01NDbXnpG2GdSN3Dq3sFuzPR

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b0aa18a21903`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.