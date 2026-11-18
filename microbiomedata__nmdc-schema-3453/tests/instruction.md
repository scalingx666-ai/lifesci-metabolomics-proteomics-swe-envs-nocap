# Issue

**Title:** Fail on repeated keys in example data, and fix the seven files that have them

## Description

Seven example data files repeat a key in the same mapping. PyYAML keeps only the last copy and silently drops the earlier ones, so part of each file was never validated. For example, `src/data/valid/Database-neon-story.yaml` had `material_processing_set` three times, and only the third list was checked. Found while reviewing  where a counter-example repeats `isotopolog_atom_pos`.

The first commit adds `tests/test_example_data_duplicate_keys.py`, which loads every file under `src/data/` with a loader that records repeated keys. It fails on the seven files on `main` and passes on the other 323.

The second commit fixes them:
- `Database-neon-story.yaml`, `Database-neon_Biosample_to_DataObject_NEON.yaml` and `Database-metatranscriptome_workflow-invalidDatabase.yaml`: the repeated collections are merged into one list. No record was removed. The previously dropped records in the two valid files now validate and pass.
- `MetatranscriptomeAnnotation-1.yaml` (`processing_institution`) and `NucleotideSequencing-instrument_name-retired.yaml` (`associated_studies`) keep the copy the loader was already using. In the second file the dropped copy was `nmdc:dgns-00-555xxx`, which isn't a study ID and would have added a second failure reason.
- `MetaproteomicsAnalysis-failure-invalid_qc_failure_what.yaml`: the two `type` lines were identical.
- `DataObject-Crisper-Terms-data_object_type.yaml`: keeps `Crispr Terms`, matching the file name and description. The loader had been keeping the other copy, `CheckM Statistics`.

The third commit makes every touched counter-example fail for exactly one reason, and links up the neon story:
- `Database-metatranscriptome_workflow-invalidDatabase.yaml`: with the merge, all four workflow records are validated. They now use `nmdc:` class URIs (the annotation record is `nmdc:MetatranscriptomeAnnotation`, not the old `MetatranscriptomeAnnotationActivity`) and give `was_informed_by` as a list, so the only error is the intended unexpected `metagenome_assembly_set`.
- `MetaproteomicsAnalysis-failure-invalid_qc_failure_what.yaml`: adds the missing required `started_at_time`, so the only error is `low_peptide_count`.
- `Database-neon-story.yaml`: the three processed samples take the IDs the Pooling, Extraction and LibraryPreparation records output (`nmdc:procsm-99-pooled`, `-extract`, `-library`), which match the samples' own names.
- The test gains a negative control: a repeated nested key that `yaml.safe_load` silently collapses has to be reported. That control fails if the custom constructor is disconnected.

Validation: `make test` passes (426 tests: 330 from the new per-file test, plus its negative control). Generated artifacts under `nmdc_schema/` are not committed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6fea28e893a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.