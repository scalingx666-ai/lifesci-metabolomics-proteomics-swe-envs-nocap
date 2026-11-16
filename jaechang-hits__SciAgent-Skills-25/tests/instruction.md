# Issue

**Title:** refactor: relocate misplaced biostatistics entries

## Description

## Summary
`biostatistics/` had become a catch-all for ML libraries, plotting, utility guides, and clinical-writing entries. Move 8 entries to categories that match their actual purpose; leave only true statistics entries (`pymc-bayesian-modeling`, `scikit-survival-analysis`, `statistical-analysis`, `statsmodels-statistical-modeling`).

### Moves (path + registry category)
- `matplotlib-scientific-plotting` → `data-visualization`
- `scikit-learn-machine-learning` → `scientific-computing`
- `shap-model-explainability` → `scientific-computing`
- `pyhealth` → `scientific-computing`
- `degenerate-input-filtering` → `scientific-computing`
- `nan-safe-correlation` → `scientific-computing`
- `clinical-decision-support-documents` → `scientific-writing`
- `hypothesis-generation` → `scientific-writing`

### Category counts after
- `biostatistics` 12 → 4 (now coherent)
- `scientific-computing` 24 → 29
- `data-visualization` 6 → 7
- `scientific-writing` 21 → 23

## Test plan
- [x] `pixi run test` passes (4135 tests, includes `test_category_matches_directory` and `test_path_matches_category`)
- [x] reviewer confirms `pyhealth` placement (healthcare ML — landed in scientific-computing as ML catch-all; alternative would be a future `medical-informatics` category)
- [x] reviewer confirms `clinical-decision-support-documents` and `hypothesis-generation` fit scientific-writing's "research ideation and brainstorming" scope

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `57d410131d27`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.