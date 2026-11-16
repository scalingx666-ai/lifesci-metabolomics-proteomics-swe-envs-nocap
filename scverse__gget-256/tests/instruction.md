# Issue

**Title:** fix(opentargets): adapt to upstream API drift + skip deprecated expressions field

## Description

Fixes the 11 opentargets tests failing across all Python versions on main. Three distinct upstream changes — addressed independently:

## 1. GraphQL schema change (real code bug) — 2 tests

```
RuntimeError: OpenTargets GraphQL returned HTTP 400.
Body: Field 'synonyms' of type '[DrugLabelAndSource!]!' must have a sub selection.
```

The Drug type's \`synonyms\` and \`tradeNames\` are now \`[DrugLabelAndSource!]!\` instead of scalar lists. Querying without a sub-selection 400s. Updated \`QUERY_STRING_DRUGS\` to query \`{ label }\` — the existing \`_collapse_singletons()\` post-processor flattens each \`{label: "X"}\` back to \`"X"\` automatically, so **the public DataFrame shape is preserved** (\`drug.synonyms\` remains \`list[str]\`).

Confirmed via GraphQL introspection: \`DrugLabelAndSource.{label, source}\` are both \`String!\`.

## 2. Data drift — 8 fixtures refreshed

Per project convention (refresh fixtures, don't normalize):

| Test | What changed upstream |
|---|---|
| \`test_opentargets\` | Disease ontology: \`EFO_0000274\` → \`MONDO_0004980\` |
| \`test_opentargets_diseases\` | Same disease ID change |
| \`test_opentargets_drugs\` | Re-captured with the synonyms fix applied |
| \`test_opentargets_interactions\` | Protein IDs (e.g. \`ENSP00000361004\` → \`ENSP00000360730\`) |
| \`test_opentargets_pharmacogenetics\` | Variant allele frequencies (\`T_C,C\` → \`T_C,T\`) |
| \`test_opentargets_depmap\` | Hash refreshed (1239 rows) |
| \`test_opentargets_depmap_filter\` | UBERON_0002367 (prostate) has no depmap data for IL13 anymore; fixture now expects \`[]\` |
| \`test_opentargets_interactions_no_limit\` | Hash refreshed (25 rows) |

Refreshed via a one-shot script that calls each function with the test args and rewrites \`expected_result\` to match.

## 3. \`expressions\` field deprecated — 2 tests skipped

Open Targets removed data from \`Target.expressions\` (returns \`[]\` for all queries). The replacement is \`Target.baselineExpression\` with a **completely different schema**:

- Old: \`expressions[].tissue.{id, label, anatomicalSystems, organs}\` + \`expressions[].rna.{zscore, value, unit, level}\`
- New: \`baselineExpression.rows[].{targetFromSourceId, max, q1, q3, median, min, tissueBiosample, celltypeBiosample, datasourceId, …}\`

Migrating \`gget_opentargets\` to the new field is a **user-facing API change** (different DataFrame columns) that warrants its own PR. For now:

- \`test_opentargets_expression\` and \`test_opentargets_expression_no_limit\` are marked \`type: "skip"\` with a \`reason\` field
- \`tests/from_json.py\` gains a new \`skip\` test type so JSON-defined tests can be skipped with a reason message (no need for a separate Python test file)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `919dab8a200b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.