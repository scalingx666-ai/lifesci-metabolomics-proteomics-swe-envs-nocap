# Issue

**Title:** Let the OLS4 embeddings search run on named classes, slots or enums

## Description

Closes  (Let the OLS4 embeddings search run on a single enum or class).

Checking candidate mappings for one enum meant searching every permissible value in the schema, which takes at least 10 minutes. That came up reviewing the 10 new `AnalysisTypeEnum` values in

`--element NAME` (repeatable) keeps only the named classes, slots or enums. For an enum, `--element-types pvs` then searches only that enum's values. A name that isn't in the schema, or that matches nothing in the selected `--element-types` (a class name with `--element-types pvs`, say), stops with an error before any search runs, so a typo can't produce an empty results file that looks like a finished run.

`src/docs/ontology-alignment-ols4.md` lists the option.

## Validation

- `tests/test_ols4_embeddings_search.py` (7 tests) runs the CLI against a small inline schema with the OLS4 call replaced, covering one enum, one enum's values only, repeated names across types, no `--element`, an unknown name, a name outside the selected types, and one such name mixed in with valid ones.
- Doctests in the script pass.
- Ran it for real on 2026-10-08: `--element AnalysisTypeEnum --element-types pvs` searched the 11 values on `main` and wrote 220 rows in 41 seconds, most of it API response time.
- `ruff check` passes on both files. I didn't reformat the rest of the script, which `ruff format` already flags on `main`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1c70a442ac5b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.