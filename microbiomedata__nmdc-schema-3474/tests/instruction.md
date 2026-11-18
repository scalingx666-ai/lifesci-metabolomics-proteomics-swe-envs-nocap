# Issue

**Title:** Remove `collection_time_inc` rows from NCBI mapping and OLS4 alignment assets

## Description

Part of  (Clean up remaining mentions of `collection_time_inc` outside the schema YAML).

 removes `collection_time_inc` from the schema YAML, but rows for the slot stay in the asset files. This PR removes those rows the same way  did for `collection_date_inc`: 1 row from each of the 4 `assets/ncbi_mappings/*.tsv` files and 20 rows from `assets/ontology_alignment/ols4_embeddings_results.tsv`. The diff only deletes rows.

It should merge together with

@sujaypatil96, the nmdc-runtime NCBI exporter reads the mapping files. Can you confirm it doesn't need a row for a slot that's still in the schema until  merges?

I didn't update the summary counts in `src/docs/ontology-alignment-ols4.md`. They were already out of date on `main` (the doc says 45,920 rows, the file had 46,020), so they need a regeneration, not a 20-row edit.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `647010882b23`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.