# Issue

**Title:** Refactor spectra collection

## Description

- `SpectraCollection` now contains fragment as `FragmentCollectionType`, implemented is only a `CSRFragmentCollection` but in principle this could also be other variants.
- New slicing options:
```python
spectra_collection[-100:, 50.0:500.0]  # --> returns the last 100 spectra, but only with fragments m/z  between 50. and 500.0
spectra_collection[72, 100:]  # --> returns Spectrum object of spectrum 72 of the collection but only containing fragments with mz 100 or larger

for s in spectra_collection:
    pass  # s will be Spectrum objects here!

```

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e05505ee463c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.