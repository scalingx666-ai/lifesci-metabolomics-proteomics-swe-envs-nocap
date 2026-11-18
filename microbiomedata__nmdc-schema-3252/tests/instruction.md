# Issue

**Title:** Fix false broad/narrow mapping direction (use related_mappings)

## Description

First batch from #3250: fix six slot mappings whose `broad`/`narrow` direction asserts a subsumption that does not hold.

Per SKOS (now documented in `CLAUDE.md`), `broad_mappings` means the target subsumes the slot and `narrow_mappings` means the slot subsumes the target. Neither holds here:

- `num_16s` / `num_5s` / `num_23s` / `num_t_rna` `broad_mappings` → OMIT rRNA/tRNA molecules: a **count** of sequences is not subsumed by the molecule it counts.
- `input_mass` `broad_mappings` → `MIXS:0000111` (dna): a sample mass is not subsumed by a dna property.
- `doi_value` `narrow_mappings` → `edam.data:1188` (DOI): inverted; DOI is not narrower than the slot.

All six become `related_mappings`, which records the associative link without the false subsumption/inversion.

Scope: this PR only removes the demonstrably wrong **direction**. The deeper slot→class type mismatches (these targets are classes; ~27 exist repo-wide) are left for owner review under #3250. Docs-adjacent only; no generated artifacts committed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3887061ef828`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.