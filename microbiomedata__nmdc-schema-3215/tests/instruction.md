# Issue

**Title:** INSDC library modeling: pin SRA source, enforce + document the SRA DataObject pattern

## Description

Follow-ups on top of  (3213 update LibraryPreparation modeling for insdc compatibility and example data for MicroFlora Danica) to make the INSDC library modeling align with the SRA standard and be clear to schema users for interchange and validation. Targets your branch so you stay the owner of the feature.

### What and why

- **Pin the SRA citation.** The `see_also` links pointed at the `master` branch of `enasequence/webin-xml` (a moving target). Pinned to tag `2.1.0`. I fetched the XSD at that tag and confirmed it resolves with the same enum values that the schema mirrors.

- **Enforce the SRA retrieval contract.** Added a rule on `DataObject`: when `data_object_type` is `SRA toolkit-accessible sequence data`, `insdc_run_identifiers` is required. Before this, the schema allowed such an object with neither a URL nor an accession, leaving no way to retrieve it. This uses the same `preconditions`/`postconditions` idiom already in the schema (DOI and chromatography rules). It only fires for the new SRA type, so it does not affect existing data.

- **Document the pattern for users.** Added a comment on the enum value explaining how to model SRA-fetched data: one run-level `DataObject`, accession in `insdc_run_identifiers`, `url`/`md5_checksum`/`file_size_bytes` omitted because retrieval is by accession through the SRA Toolkit, not by a stable URL.

- **Mark the partial enums deliberate.** Noted that `LibraryStrategyEnum` and `LibrarySelectionEnum` are curated subsets of the INSDC vocabulary. Verified against the XSD: `LibrarySourceEnum` already matches it exactly (9/9); strategy is 4/40 and selection is 6/31, with exact token casing in all cases.

- **Typos + example alignment.** Fixed `avaliable` and `rRN`.

### Please confirm: the example DataObject rename

I changed the example DataObject from `name: file manfiest for run...` / `Manifest file for the SRR27943095 run` to a sequence-data wording, because the name and description said "manifest" while `data_object_type` says `SRA toolkit-accessible sequence data`, and a manifest (a listing of files) is a different thing from the sequence data. You have called it a "manifest" consistently since the first commit, so if you genuinely meant a manifest file, the right fix is the opposite of mine: change or add a `data_object_type` rather than the name. Your call.

### Not done locally

I did not run `make all && make test`; CI is the gate. The new rule is satisfied by the example (it has `insdc_run_identifiers`).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7995a4d2de42`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.