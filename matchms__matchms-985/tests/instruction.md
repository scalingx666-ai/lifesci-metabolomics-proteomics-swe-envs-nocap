# Issue

**Title:** Use the adduct charge in correct_charge before guessing from ionmode

## Description

If a spectrum has no charge but has an adduct like `[M-2H]2-` or `[M+2H]2+`, the default pipeline sets its charge to -1 or +1:

```python
s = Spectrum(mz=..., intensities=...,
             metadata={"precursor_mz": 500.25, "ionmode": "negative", "adduct": "[M-2H]2-"})
SpectrumProcessor(DEFAULT_FILTERS).process_spectrum(s).get("charge")
# 0.33.1 and master: -1   (parent_mass is computed correctly from the adduct, so the two now disagree)
```

MassBank MSP records are exactly this case: they give `Precursor_type` and `Ion_mode` but no charge.

Why: in `filter_order.py`, `correct_charge` runs before `clean_adduct`. With no charge, `correct_charge` guesses +1 or -1 from the ionmode. `clean_adduct` only takes the charge from the adduct when the charge is missing, so by then it just logs "The charge in the adduct ... and the given charge ... do not match".

Fix: when there is no charge (or it is 0), `correct_charge` first takes it from the adduct (via `_clean_adduct` and `get_charge_of_adduct`), and only then falls back to guessing from the ionmode. The existing step that makes the sign agree with the ionmode is unchanged.

Tested:

- Six new cases in `test_correct_charge.py`, including one that runs the whole `DEFAULT_FILTERS` pipeline. Five fail on master and all pass with the fix.
- Full suite: 1441 passed, 2 skipped before. 1447 passed, 2 skipped after.
- Real data, `DEFAULT_FILTERS` on the full MassBank 2026.03 open MSP plus 38 GNPS libraries (104,574 spectra kept): spectra whose final charge disagrees with their adduct went from 342 to 274. In MassBank the count went from 77 to 12. The 65 fixed spectra are 33 `[M+2H]2+`, 27 `[M-2H]2-` and 3 `[M]2+` that had been set to ±1, plus 2 more. The remaining mismatches are conflicts in the source data, for example `[M-H]-` recorded in positive mode, which this filter is meant to leave to the ionmode.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `50baefdb0ce9`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.