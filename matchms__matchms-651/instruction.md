# Issue

**Title:** Save mgf msp once per iteration in pipeline

## Description

Addresses issue #646, which is also an issue for me. Added an extra `append` boolean kwarg to `save_spectra`, and conditionally allowed saving processed spectra inside the `process_spectrums` (depends on filetype). MGF and MSP file types now automatically get written "line-by-line". 

I refrained from adding an extra param to `process_spectrums`. I think it's better to leave the function arglist to a minimum.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `411da2b669df`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.