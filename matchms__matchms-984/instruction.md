# Issue

**Title:** Read MSP records with Num Peaks: 0 instead of merging them into the next one

## Description

`load_from_msp` drops a record with `Num Peaks: 0`, and the next spectrum in the file inherits that record's metadata. matchms writes such records itself: `save_as_msp` writes `NUM PEAKS: 0` for a spectrum with no peaks. So a save and load round trip gives the wrong structure to a different spectrum:

```python
a = Spectrum(mz=np.array([]), intensities=np.array([]),
             metadata={"compound_name": "A", "precursor_mz": 300.1, "smiles": "c1ccccc1"})
b = Spectrum(mz=np.array([50., 60.]), intensities=np.array([1., 2.]),
             metadata={"compound_name": "B", "precursor_mz": 400.2})
save_as_msp([a, b], "x.msp")
[(s.get("compound_name"), s.get("smiles")) for s in load_from_msp("x.msp")]
# 0.33.1 and master: [('B', 'c1ccccc1')]   (A is gone, and B now has A's SMILES)
```

The MGF round trip of the same two spectra is correct.

Why: `parse_msp_file` only ends a record when the number of peak lines reaches `num peaks`. With `Num Peaks: 0` there are no peak lines, so the record never ends and its `params` dict carries over into the next record. Keys the next record does not set itself (SMILES, formula, InChIKey and so on) keep the old values.

Fix: when the `Num Peaks` line says 0, end the record right there and yield it as a spectrum with no peaks. Building the yielded dict is moved into a small helper so both paths share it. Files that put metadata after a non-zero `Num Peaks` line keep their current behavior.

Tested:

- Two new tests: an MSP file with a zero-peak record followed by a normal one, and the `save_as_msp` round trip above. Both fail on master and pass with the fix.
- Full suite (`tests`, with `test_flash_similarity_ms_entropy_parity.py` ignored because ms_entropy is not installed): 1441 passed, 2 skipped before. 1443 passed, 2 skipped after.
- No change on real files: the full MassBank 2026.03 open MSP (96,949 records), 17,045 Enveda-180 records and all MSP test data in the repo load byte-identical before and after (114,027 spectra, same peaks-and-metadata hash `6c17f7e05ce73ecf`).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7d960b001e52`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.