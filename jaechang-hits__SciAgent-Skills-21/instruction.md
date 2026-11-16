# Issue

**Title:** feat: add bakta and roary skills for gene annotation and pan-genome analysis

## Description

## Summary

Adds two pipeline skills to `genomics-bioinformatics/` to cover the prokaryotic gene-annotation → pan-genome-clustering workflow that was previously missing from the registry:

- **`bakta-genome-annotation`** — bacterial/archaeal genome and plasmid annotation via Prodigal/HMM/DIAMOND against a curated UniRef-derived database. Covers light/full DB setup, JSON/TSV/GFF3 parsing, Circos plot rendering, MAG and plasmid modes. 8 workflow steps, 4 recipes.
- **`roary-pangenome`** — bacterial pan-genome computation from Prokka/Bakta GFF3 via CD-HIT + BLASTP + MCL. Covers presence/absence parsing, core/soft-core/shell/cloud partitioning, core-gene alignment for phylogenetics, and a Fisher-exact phenotype-association recipe. 8 workflow steps, 4 recipes.

Both skills cross-reference each other and existing `prokka-genome-annotation` / PGAP / Panaroo / PIRATE / PPanGGOLiN entries for routing guidance.

Registry: 197 → 199 entries.

## Checklist

- [x] `pixi run test` passes locally (4135 passed, 0 failed)
- [x] `registry.yaml` updated with the new entry
- [x] Skill type is correctly set: pipeline / toolkit / database / guide
- [x] `description` field is ≤ 1024 characters
- [x] Frontmatter has `name`, `description`, `license`
- [x] Required sections present in correct order (see `CLAUDE.md`)
- [x] Code blocks are runnable with sample data or clear placeholders
- [x] Troubleshooting table has 5+ rows
- [x] Key Parameters table has 5+ rows

## Skill(s) added or modified

- `skills/genomics-bioinformatics/bakta-genome-annotation/SKILL.md` (new)
- `skills/genomics-bioinformatics/roary-pangenome/SKILL.md` (new)
- `registry.yaml` (modified — appended two entries)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `760aeb6c2aaa`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.