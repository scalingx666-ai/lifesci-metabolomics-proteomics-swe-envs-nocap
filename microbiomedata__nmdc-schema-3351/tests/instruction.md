# Issue

**Title:** Remove slot_usage assertions that restate inherited values

## Description

Closes

Removes 68 of the 69 `slot_usage` assertions that restate a value the class already inherits. The induced slot is unchanged by every one of them; what they cost is that an edit to the parent silently stops reaching each class that restated the old value.

Pure deletions, 140 lines, no additions to the schema.

| commit | what |
|---|---|
| `598ca79` | 31 `id.required: true` restatements |
| `33436d9` | `has_input` / `has_output` from `MaterialProcessing`, and `Biosample` restating `Sample` |
| `8ed7149` | the gate and a ratchet test |

Nine `slot_usage` entries had every metaslot flagged, so the slot key went with them.

## How this is verified

Diffing `nmdc_schema/nmdc_materialized_patterns.yaml` does not answer the question. It is built with `--no-materialize-attributes`, so per-class induced slots are never expanded, and a changed inherited `required` or `range` would not appear in it.

`src/scripts/dump_induced_slots.py` expands them: 18408 rows in about a second. Run before and after, the diff is empty. That is the proof that nothing here changed meaning, for every class and slot at once rather than a sample.

```bash
make assets/induced-slots.tsv   # before
# apply the change
make assets/induced-slots.tsv   # after, then diff
```

It is deliberately not a prerequisite of any other target, since it is a hand-run gate rather than a build artifact. Reusable for any future refactor claiming to preserve meaning.

`linkml validate src/schema/nmdc.yaml` reports no issues, and the Python tests pass.

## The one kept, and why

`PropertyAssertion.has_unit.required: false` stays. Its baseline is unset rather than asserted, so it restates a default rather than a value, and it documents the conditional requirement its own description spells out ("required only when numeric value is present"). If `AttributeValue` ever requires `has_unit`, that assertion stops being a restatement and becomes a genuine relaxation, so the marker is worth keeping.

Related: no `slot_usage` in the schema relaxes an inherited constraint today. Checked `required` true to false and loosened `minimum_value` / `maximum_value`; zero hits.

## Ratchet rather than snapshot

`tests/test_no_redundant_slot_usage.py` asserts nothing redundant exists beyond that one documented exception, so a new one fails in CI instead of accumulating. A committed snapshot of all 18408 values would instead need regenerating on every legitimate schema change and would fail loudly for correct work.

## Follow-up, not in this PR

`src/docs/maintaining-the-schema.md` cites re-declaring the `uriorcurie` range as deliberate belt-and-suspenders practice. No class does that in a `slot_usage`, so the example needs replacing with a real one.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `84651fe32b2e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.