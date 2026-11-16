# Issue

**Title:** feat: add know-how skills migrated from omics-horizon-agent

## Description

## Summary
- Migrate 6 domain best-practice guides from `ohagent/know_how/` (in the omics-horizon-agent repo) to `skills/know-how/` here:
  - `omics-analysis-guide`, `sar-analysis`, `scientific-literature-search`, `sgrna-design-guide`, `single-cell-annotation`, `western-blot-quantification`
- Move the two data files referenced by the sgRNA guide into `skills/know-how/sgrna-design-guide/resource/`:
  - `addgene_grna_sequences.csv` (300+ validated sgRNAs from Addgene)
  - `CRISPick_download_links.txt` (238 CRISPick precomputed library URLs)
- Update path references inside `sgrna-design-guide/SKILL.md` from `ohagent/know_how/resource/...` to skill-relative `resource/...`

## Why
The `KnowHowLoader` path in `omics-horizon-agent` (loading these markdown docs directly via a Python loader) is being retired. With this PR, these guides flow through the unified skills system (`OmicsSkillsMiddleware` + deepagents skills routing) like the other 195+ skills. Removes the duplicate loading path and centralizes domain guides in one place.

## Test plan
- [ ] `pixi run test` passes (registry/frontmatter/content checks)
- [ ] Spot-check `sgrna-design-guide/SKILL.md` — `pd.read_csv('addgene_grna_sequences.csv')` and `grep ... resource/CRISPick_download_links.txt` references resolve relative to the skill directory
- [ ] Companion PR in `omics-horizon-agent` removes `ohagent/know_how/` entirely; agent boot smoke test (uvicorn) passes with no `KnowHowLoader` ImportError

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `86e11b73be7f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.