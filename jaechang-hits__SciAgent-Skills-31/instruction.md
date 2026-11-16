# Issue

**Title:** feat: add smina + mdtraj skills (structural biology)

## Description

## Summary

Adds two new SciAgent skills under `skills/structural-biology-drug-discovery/`.

- **`smina-molecular-docking`** (pipeline, GPL-2.0) — AutoDock Vina fork. Adds custom scoring (`--custom_scoring`), local optimization (`--local_only`), autoboxing, native SDF/MOL2 input, per-atom score decomposition. Distinct from `autodock-vina-docking` (Python API + Vinardo) and `diffdock-blind-docking` (unknown binding site).
- **`mdtraj-trajectory-analysis`** (toolkit, LGPL-2.1) — MD trajectory analysis covering RMSD vs time / radius of gyration / per-residue RMSF (multi-replicate), residue-residue contact frequency maps, Ramachandran plots (general + Gly + Pro), and 8-state DSSP secondary-structure time series. Distinct from `mdanalysis-trajectory` (richer atom-selection grammar, AnalysisBase framework).

## How it was authored

Both entries were scaffolded via `.claude/skills/sciagent-skill-creator` — the skill-creator triggered correctly on each "add a SciAgent skill for X" prompt and generated the frontmatter + registry append before content was filled in. ChEMBL and UniProt requests were skipped after duplicate detection surfaced existing entries (`chembl-database-bioactivity`, `uniprot-protein-database`).

## Content depth

| Entry | Sub-type | Code blocks | Param rows | Troubleshoot rows |
|-------|----------|-------------|------------|-------------------|
| smina-molecular-docking | pipeline | 12 (Quick Start + 8 workflow steps + 4 recipes) | 16 | 11 |
| mdtraj-trajectory-analysis | toolkit | 16+ across 6 Core API modules + 2 workflows + 4 recipes | 11 | 11 |

The mdtraj headline Common Workflow implements the requested multi-replicate analysis end-to-end: RMSD/Rg in Å for three replicates, per-residue RMSF, contact frequency map (white→blue), Ramachandran density (blue→white→red), Gly/Pro-specific Ramachandran (blue→red), and DSSP 8-state evolution with the exact pastel color scheme (white coil, pastel red sheet, black bridge, pastel green bend, pastel yellow turn, pastel blue α-helix, pastel purple π-helix, grey 3_10).

## Test plan

- [x] `pixi run test` — 4096 passed (24 new tests for mdtraj toolkit structure; smina passes the pipeline checks)
- [x] `pixi run validate` — registry well-formed
- [x] Manual: frontmatter description first 120 chars lead with tool name, no stop-verb start, no promotional adjectives
- [x] Manual: registry description in sync with SKILL.md frontmatter for both entries
- [ ] Reviewer to spot-check a workflow code block against current mdtraj / smina API docs

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `04595ba37716`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.