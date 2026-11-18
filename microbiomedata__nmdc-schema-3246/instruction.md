# Issue

**Title:** Rename TargetGeneEnum to TargetGeneOrLocusEnum; add rRNA operon values

## Description

## Why

`target_gene`'s range (`TargetGeneEnum`) enumerated only single rRNA genes (16S/18S/23S/28S). The microflora danica amplicon study (PRJNA1071982), the first amplicon data being brought into NMDC, sequences whole rRNA operons: NCBI's SRA design descriptions label them "bacterial rRNA operons" (8F/2490R) and "eukaryotic rRNA operons" (3NDF/21R). Those had no valid permissible value.

## What

- Add `bacterial_rRNA_operon` and `eukaryotic_rRNA_operon`.
- Rename the enum to `TargetGeneOrLocusEnum`, since it now covers loci larger than a single gene. MIxS already defines the slot as "targeted gene or locus name for marker gene studies," so this stays within its intent. An enum comment records that reasoning.
- Add Sequence Ontology `meaning:` to the four existing rRNA values (`SO:0001000`, `SO:0001001`, `SO:0000407`, `SO:0000653`).
- Replace the stale MIxS free-text example (`16S rRNA, 18S rRNA, nif, amoA, rpo`, which mixes non-permissible values and a formatting variant) with valid values, surfacing both operon PVs. Closes the example mismatch in #3240.
- Add a `nif` counter-example under `src/data/invalid/`.

The enum and range override are injected during the MIxS build (`makefiles/mixs.Makefile`), not hand-edited in `mixs.yaml`. Generated `nmdc_schema/` artifacts are intentionally not committed here.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1e86e5b382f6`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.