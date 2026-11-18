# Issue

**Title:** Document the mapping metaslots in one place and correct the mappings on 19 slots

## Description

## Why

This PR closes no issue. Part of:

-
-

The mapping rules were spread over `CLAUDE.md` and two docs pages, and the `CLAUDE.md` copy had errors: a `broad_mappings` example on a value that has no mappings, and a class mapping called property-to-property. One docs section now holds them.

That section says a slot maps to a property where one exists. Where an ontology models a data field only as a class, the slot may name that class in `close_mappings` when each value of the slot is an instance of what the class describes, otherwise in `related_mappings`, and in no other mapping metaslot, because `exact_mappings`, `broad_mappings` and `narrow_mappings` assert identity or subsumption between a property and a class, and generic `mappings` stays for the schema.org, QUDT and PROV alignments. The 19 slots on main with class mappings elsewhere are moved to match, and those moves are the part to review.

I asked for a test of the rule in the following issue and decided against it, because it needed an OLS4 class-or-property lookup recorded for every mapped term, starting with the 69 GENEPIO terms in the following PR. The rule is documentation only, and I'm closing the issue as not planned.

-
-

## What changed

- 16 slot `exact_mappings` to ontology classes move. 8 become `close_mappings`: `doi_value`, `input_mass`, `ionization_source`, `library_preparation_kit`, `mass_analyzers`, `mass_spectrometry_acquisition_strategy`, `number_of_contig` and `pcr_cycles`. 8 become `related_mappings`: the seven `gtdbtk_*` slots, whose TAXRANK terms are ranks rather than names, and `mass`, since a measured quantity isn't the quality PATO:0000125.
- 2 generic `mappings` become `close_mappings`: `objective` (SIO:000337) and `processing_institution_workflow_metadata` (NCIT:C165211).
- `extraction_targets` moves NCIT:C177560 (Nucleic Acid Extraction Method) and MIXS:0000037 (`nucl_acid_ext`, a method reference) from `narrow_mappings` to `related_mappings`, because neither is a narrower extraction target.
- `doi_value` moves edam.data:1188 (DOI) from `related_mappings` to `close_mappings`.
- Stored records carry no mappings, so there is no migration. On 2026-10-28 nothing outside nmdc-schema read these mapping metaslots (I checked nmdc-runtime, nmdc-server, submission-schema, nmdc_automation, nmdc-lakehouse and GitHub code search), and submission-schema main (79217015f) defines none of these slots.

## Validation

`make all test` exits 0 with 660 passed (2026-10-28). The regenerated `nmdc_schema/` files stay uncommitted, as this repo does for development PRs.

## Documentation impact

The rules are in "Mapping schema elements to external terms" in `src/docs/maintaining-the-schema.md`, with a table of the six metaslots and their SKOS predicates. `CLAUDE.md` and `src/docs/ontology-governance-current-state.md` point to it instead of restating them.

## Scope and complexity

Mapping metaslot keys on 19 slots, and prose in three docs files.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `76fa030241c0`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.