# Issue

**Title:** Correct two documented facts about slot_usage cascading and readonly metaslots

## Description

Closes

Two documented facts did not match the schema, and both produced wrong conclusions in the last day.

**The belt-and-suspenders passage.** `maintaining-the-schema.md` justified restating an inherited value on the grounds that cascading "may not always be the case", and offered re-declaring the `uriorcurie` range as the example. No class re-declares `id.range` in a `slot_usage`, so the example did not exist, and the premise does not hold either: constraints written in a class `slot_usage` do cascade through `is_a`. That passage was cited as authority in  and

Replaced with the current practice, which is the opposite: restatements are reported by `report_redundant_slot_usage.py` and a new one fails CI in `test_no_redundant_slot_usage.py`. The real failure mode is kept, with a pointer to it: slot-level `is_a` does drop a falsy value such as `minimum_value: 0`, which is  and does not affect class `slot_usage`.

**The readonly metaslots.** `developer-docs.md` and `CLAUDE.md` both listed all 12 without saying they span two metamodel element types. Only 7 are on `SlotDefinition`; `generation_date`, `metamodel_version`, `source_file`, `source_file_date`, and `source_file_size` are `SchemaDefinition` and never appear on a slot, even after induction. A reviewer read the list as slot-level and reported a defect in `report_redundant_slot_usage.py` that could not occur, rebutted at

Both splits verified against `fields(SlotDefinition)` and `fields(SchemaDefinition)`: the 7 and the 5 are disjoint and total 12.

Docs only, no schema or code changes.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2a6caf293471`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.