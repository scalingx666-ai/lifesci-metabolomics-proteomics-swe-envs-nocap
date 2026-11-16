# Issue

**Title:** fix: strip palette leaks, audit skill-creator, compress smina+mdtraj

## Description

## Summary

Three-commit follow-up to . Triggered by the observation that the merged `mdtraj-trajectory-analysis` skill baked palette choices (hex codes, custom cmaps, DSSP 8-state pastel scheme) that don't belong in a tool skill, and that both `smina` and `mdtraj` were unnecessarily verbose.

1. **`fix(mdtraj)`** — strip hex color codes and cmap definitions from mdtraj Workflow 1: drop the per-replicate `colors` dict, both `LinearSegmentedColormap.from_list(...)` palettes (contact map, Ramachandran), the `dssp_colors` 8-state pastel dict, the `ListedColormap`/`Patch` legend block, and the now-unused `matplotlib.colors`/`seaborn` imports. Save the DSSP code-order mapping to `.npz` so consumers can render their own legend.

2. **`refactor(skill-creator)`** — audit the scaffolder for generalizability:
   - Add a "Content authoring rules (what NOT to bake into a SKILL.md)" section to `.claude/skills/sciagent-skill-creator/SKILL.md` listing the leak patterns: color palettes, per-condition color dicts, DPI/figure-size presets, one-shot user-brief specifics, hardcoded user paths. Includes the heuristic *"if a downstream consumer would override the choice, don't ship the choice in the skill."*
   - Drop dead `STOP_VERBS` constant from `scaffold.py` (defined but never referenced; the check lives in `validate_description.py`).
   - Add a "Plotting: use library defaults" note to `SKILL_TEMPLATE.md` and `SKILL_TEMPLATE_TOOLKIT.md` header comments.

3. **`refactor(skills)`** — compress smina and mdtraj without dropping technical substance:
   - smina: **443 → 376 lines (-15%)**
   - mdtraj: **568 → 449 lines (-21%)**
   - Tighten Overview / When to Use / Prerequisites prose
   - Trim one-liner step descriptions
   - Drop redundant in-code commentary
   - Replace mdtraj's former "Module 6: Visualization Helpers" (which prescribed `plt.rcParams` style) with "Module 6: Hydrogen Bonds and SASA", absorbing the old Workflow 2 H-bond block into Core API; Workflow 2 is now a multi-replicate H-bond/SASA summary
   - Keep all code-block, parameter-row, and troubleshooting-row counts above the test-suite thresholds

## Test plan

- [x] `pixi run test` — 4096 passed
- [x] `pixi run validate` — registry well-formed
- [x] Confirmed no hex codes / `LinearSegmentedColormap` / `ListedColormap` / `plt.rcParams.update` remain in either skill (only legitimate `colorbar` API calls)
- [x] Routing-guidance bullets retain the `"instead"` keyword required by `test_pipeline_when_to_use_has_routing_guidance` and `test_toolkit_when_to_use_has_alternative_comparison`
- [ ] Reviewer to spot-check a workflow block in each compressed skill still runs as documented

## Diff stat

```
.claude/skills/sciagent-skill-creator/SKILL.md     |  14 +
.../sciagent-skill-creator/scripts/scaffold.py     |   3 +-
.../mdtraj-trajectory-analysis/SKILL.md            | 508 +++++++-------------
.../smina-molecular-docking/SKILL.md               | 315 ++++---------
templates/SKILL_TEMPLATE.md                        |   7 +-
templates/SKILL_TEMPLATE_TOOLKIT.md                |   7 +-
6 files changed, 335 insertions(+), 519 deletions(-)
```

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d3d04b27f29c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.