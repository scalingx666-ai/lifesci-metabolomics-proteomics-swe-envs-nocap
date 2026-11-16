# Issue

**Title:** Use SpectraCollection for faster score computation (1st case: FlashSimilarity)

## Description

- Instead of converting a list of `Spectrum` objects into a Flash-Index, we can do this quicker if we start from the CSR-based representation in `SpectraCollection`.
- The matrix() function now internally also switches the spectra1 vs spectra2 order depending on what computes faster (this makes a very notable difference if spectra1 and spectr2 have very different number of spectra).

I benchmarked this against the former FlashEntropy / CosineFlash implementation and this is notably faster (mostly in the Index computation, so the relative gain is larger for smaller datasets than for very large ones).

The "old" implementations remain in `flash_similarity_spectrum_list.py` and `flash_utils_spectrum_list.py`, at least for now. They can probably be removed in the near future.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `37b62f4f460e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.