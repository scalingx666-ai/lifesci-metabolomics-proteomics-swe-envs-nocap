# Issue

**Title:** fix(opentargets): repoint expression to baselineExpression (upstream retired target.expressions)

## Description

## Summary
Fixes `gget opentargets -r expression`, which has returned empty results since OpenTargets data release 26.06 (24 June 2026): OpenTargets intentionally retired the `target.expressions` GraphQL field and moved the data to the new `target.baselineExpression` field. This PR repoints gget's query to `baselineExpression`.

## Upstream confirmation (Open Targets staff)
Confirmed on the OT community forum: https://community.opentargets.org/t/target-expressions-returns-empty-as-of-26-06-has-it-been-replaced-by-baselineexpression/2043/2

1. `target.expressions` was **intentionally retired** in favour of `target.baselineExpression`;
2. `expressions` will be **deprecated/removed**;
3. `baselineExpression` is the **recommended** field for baseline RNA/protein expression going forwards.

Empirically: `target.expressions` returns `[]` for every gene tested (including ubiquitously-expressed housekeeping genes GAPDH/ACTB) while `target.baselineExpression` is populated; API `dataVersion` = 26.06.

## ⚠️ Output schema change (not a 1:1 port)
- Old `expressions`: per-tissue RNA **z-score** + level (Expression Atlas / Human Protein Atlas).
- New `baselineExpression`: per-biosample **TPM** summary stats (median/min/q1/q3/max), at tissue **and** cell-type level (GTEx / Tabula Sapiens / DICE / PRIDE).

The old z-score data no longer exists upstream; this adopts the dataset OpenTargets now provides.

## Testing
4 network-free mocked tests for the new parse path + live verification (`http_json` returns populated rows); removed 2 now-invalid live exact-match expression fixtures. Note (per OT staff): the new dataset is fresh and may have "teething issues".

. CI context: #243.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7ea5996dfe52`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.