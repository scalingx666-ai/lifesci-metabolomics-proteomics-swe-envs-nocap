# Issue

**Title:** feat: introduce medical-imaging category

## Description

## Summary
`cell-biology/` had become a mix of cell-level microscopy and clinical medical imaging. Split out 7 entries into a new `medical-imaging/` category so `cell-biology` stays focused on cell/microscopy biology (cellpose, flowio, napari, opencv, pyimagej, scikit-image, trackpy, single-cell-annotation) and `medical-imaging` owns DICOM/WSI/3D-volume/radiology workflows.

### Moves (cell-biology → medical-imaging)
- `pydicom-medical-imaging`
- `nnunet-segmentation`
- `histolab-wsi-processing`
- `imaging-data-commons`
- `omero-integration`
- `simpleitk-image-registration`
- `pathml`

### Other changes
- `registry.yaml`: category + path updated for all seven entries
- `CLAUDE.md` Step 2: new `medical-imaging` row added to the category table; `cell-biology` description tightened to reflect the narrower scope

### Category counts after
- `medical-imaging` 0 → 7 (new)
- `cell-biology` 15 → 8 (cell/microscopy only)

## Test plan
- [x] `pixi run test` passes (4135 tests, includes `test_category_matches_directory` and `test_path_matches_category`)
- [x] reviewer confirms category name (`medical-imaging` vs alternatives like `medical-imaging-radiology`, `clinical-imaging`)
- [x] reviewer confirms whether `cellpose-cell-segmentation` should also move (currently stays in cell-biology since its primary use is live-cell fluorescence microscopy, not clinical/radiology imaging)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `57d410131d27`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.