# Issue

**Title:** refactor: audit Related Skills sections — fix stale cross-references

## Description

## Summary
Every SKILL.md cross-reference must resolve to a registered entry name in `registry.yaml`. Stale refs send agents on dead-end loads and hurt discovery (the broken token sometimes also confuses the LLM into hallucinating a tool that does not exist).

## Audit method
- Extracted every kebab-case token from SKILL.md files in backtick / bold / list-bullet positions
- Diffed against the 197 registered names and the 4 `legacy/` names
- Manually verified each candidate against context to rule out package names, algorithm names, and other false positives

## Findings
- **`legacy/` refs**: 0 (already cleaned in #24)
- **stale name-drift refs**: 9 distinct wrong names, 20 occurrences across 9 SKILL.md files + registry.yaml

## Substitutions

| Wrong | Correct | Occurrences |
|---|---|---|
| `anndata-annotated-data` | `anndata-data-structure` | 3 files |
| `pubchem-database` | `pubchem-compound-search` | 1 |
| `chembl-database` | `chembl-database-bioactivity` | 2 |
| `alphafold-database` | `alphafold-database-access` | 3 (2 SKILLs + registry) |
| `gget-genomic-data` | `gget-genomic-databases` | 1 |
| `datamol-molecular-toolkit` | `datamol-cheminformatics` | 2 |
| `rdkit-molecular-toolkit` | `rdkit-cheminformatics` | 2 |
| `diffdock-blind-docking` | `diffdock` | 3 (2 SKILL + registry) |
| `dgidb-database` | `opentargets-database` | 3 (cbioportal SKILL + registry) |

### Special case: `dgidb-database`
DGIdb (Drug-Gene Interaction Database) is not registered. Picked the closest registered equivalent:

| Candidate | DGIdb fit |
|---|---|
| **`opentargets-database`** ⭐ | Open Targets aggregates DGIdb as one of 20+ sources, indexes by gene symbol, fits cBioPortal's cancer-genomics context |
| `drugbank-database-access` | drug-centric (DrugBank XML focuses on drugs-as-molecules + DDI), not gene-centric |
| `chembl-database-bioactivity` | bioactivity measurements (IC50/Ki), different angle |
| `pytdc-therapeutics-data-commons` | ML benchmark datasets, not interactive lookup |

If a dedicated DGIdb entry lands later, those three references can be flipped back.

## Safety
Substitutions used word-boundary-aware regex (negative lookbehind/lookahead on `[a-z0-9-]`) and were applied **longest-first** to prevent partial matches between names with shared prefixes — for example, `chembl-database` would otherwise match inside `chembl-database-bioactivity`.

Post-fix re-scan: 0 stale refs remain.

## Files touched
- `skills/genomics-bioinformatics/databases/bioservices-multi-database`
- `skills/genomics-bioinformatics/databases/cbioportal-database`
- `skills/genomics-bioinformatics/single-cell/cellxgene-census`
- `skills/proteomics-protein-engineering/esm-protein-language-model`
- `skills/proteomics-protein-engineering/uniprot-protein-database`
- `skills/scientific-computing/zarr-python`
- `skills/structural-biology-drug-discovery/molfeat-molecular-featurization`
- `skills/structural-biology-drug-discovery/smina-molecular-docking`
- `skills/systems-biology-multiomics/lamindb-data-management`
- `registry.yaml`

## Out of scope (deferred)
- **One-way link audit** (A → B but not B → A) — separate PR if pursued
- **Missing-ref additions in same category cluster** — would require taste, not mechanical fix
- **Format unification** (`` `name` `` vs `**name**` vs plain) — cosmetic
- **Pipeline sub-type `## Related Skills` policy** — currently optional in CLAUDE.md format rules

## Test plan
- [x] `pixi run test` passes (4096 tests)
- [x] post-fix audit re-run shows 0 stale refs, 0 legacy refs
- [x] reviewer confirms `dgidb-database` → `opentargets-database` is the right closest equivalent
- [ ] reviewer suggests a follow-up lint test that auto-fails CI on any kebab-case backtick/bold token in SKILL.md that isn't in `registry.yaml`

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3e3f99859234`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.