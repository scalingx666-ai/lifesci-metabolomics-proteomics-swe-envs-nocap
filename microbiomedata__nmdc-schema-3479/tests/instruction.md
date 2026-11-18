# Issue

**Title:** Scan for retired element names in files nothing checks

## Description

Part of  (Find and clean up mentions of retired schema elements in files nothing checks). Stacked on  which adds the catalog this scan reads.

When an element is removed, the schema YAML, the example data and the tests stop using it, because something checks them. `assets/`, `src/docs/`, notebooks, `src/scripts/` and the Makefiles have no such check, so old names stay there. This PR adds `make retired-element-mentions`, which writes the lines that mention a retired name to `local/retired_element_mentions.tsv`. It is a lead list, not a pass/fail check, because some files mention old names on purpose.

By default it skips names that are ordinary lowercase words or phrases (`soil`, `used`, `part of`). Early versions used many of these as element names, and they match ordinary text. `--plain-words` includes them.

## Current output

On this branch, the scan checks 458 names and finds 1,097 lines in 27 files. The largest (counted as distinct lines):

- `assets/ontology_alignment/ols4_embeddings_results.tsv`: 353
- `assets/ncbi_mappings/` (5 files): 540
- `src/docs/v10-vs-v11-retrospective.md`: 93, which is history and should stay
- `notebooks/mongo_doc_top_slot_usage_counts.ipynb`: 35, saved output
- `src/scripts/nmdc_database_tools.py`: 28
- `src/docs/mixs-v6.3.0-customizations.md`: 4

The cleanup will come in later commits on this branch, grouped by directory, along with a list of the files whose mentions are intentional.

Related:  (Add to deprecation process docs). This PR does not change the deprecation guide.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `37fa139dab6c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.