# Issue

**Title:** Add optional smoothing to local maximum mass detector

## Description

Add optional smoothing to local max mass detector

Zero values are currently not preserved, as it is only for finding maxima and minima. would be nicer for the visual fit, but as it is not differentiated between processing and preview, it would cost performance. 
Maxima and edge detection is applied to the potentially smoothed intensities, while intensity calculation is applied to the raw intensities.
<img width="1493" height="538" alt="image" src="https://github.com/user-attachments/assets/1612dfef-7ddc-4b09-b1a8-beb4b7b3dc7c" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c5baff0f8307`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.