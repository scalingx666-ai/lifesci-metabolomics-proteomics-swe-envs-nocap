# Issue

**Title:** Auxiliary changes to support safe deprecation of `collection_date_inc`

## Description

Here are the main changes that were made on this PR to support the safe and comprehensive deprecation of the `collection_date_inc` slot:

- [x] Delete `assets/misc/neon_nmdc_term_mapping.tsv` file which contained a reference to `collection_date_inc`
  - [x] Checked `nmdc-runtime` to see if any of the NEON translators reference/use this file -- answer is no, so it's okay to delete this
- [x] Remove  `collection_date_inc` mapping rows from the NCBI Attribute/NMDC slot mapping files
  - [x] These files need to be retained b/c the NCBI XML exporter in the `nmdc-runtime` repo still use them
- [x] Made updates to the OLS4 embeddings and ontology alignment files
  - [x] Ran the commands in `makefiles/ontology-alignment.Makefile` to regenerate the files
  - [x] @turbomam can you confirm that these artifacts have been regenerated correctly
- [x] Bundled in the the migrator we would need for this the deprecation into the v11.23 -> v11.24 migrator we have in the repo already
  - [x] @eecavanna can you check that the migrator looks good for this work

CC: @JamesTessmer I have an auxiliary PR here with changes that will need to accompany your PR. Feel free to pile on commits as you need or review/approve/merge.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `acfef1b7ff7b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.