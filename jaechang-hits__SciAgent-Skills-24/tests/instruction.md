# Issue

**Title:** refactor: retire duplicate skills to legacy/

## Description

## Summary
Move 4 deprecated duplicates out of `skills/` and into a new `legacy/` directory at repo root (excluded from registry and from `test_all_skill_files_registered`):

- `plotly-interactive-visualization` → keep `plotly-interactive-plots` (newer, 837 vs 485 lines, richer Core API)
- `seaborn-statistical-visualization` → keep `seaborn-statistical-plots` (newer, 819 vs 468 lines)
- `opentrons-integration` → keep `opentrons-protocol-api` (official API naming, 650 vs 431 lines)
- `single-cell-annotation` (cell-biology) → keep `single-cell-annotation-guide` (genomics-bioinformatics, actionable decision framework with CellTypist/popV tiers)

`biopython-{molecular-biology,sequence-analysis}` pair retained — they cover distinct sub-aspects (PCR/cloning/structure vs SeqIO/BLAST/MSA) with mutual cross-refs.

Cross-references in 7 other SKILL.md files and one registry description updated to point at the surviving entries.

`legacy/` lives at repo root so `test_all_skill_files_registered` (which rglobs `skills/`) does not flag the moved files.

## Test plan
- [x] `pixi run test` passes (4047 tests)
- [ ] reviewer confirms `legacy/` placement vs deleting outright
- [ ] reviewer scans for any remaining external references to retired names

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `57d410131d27`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.