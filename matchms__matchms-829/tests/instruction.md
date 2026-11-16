# Issue

**Title:** Add BLINK score implementation

## Description

This is to have fast cosine estimates in matchms and is based on [Harwood et al. (2023)](https://www.nature.com/articles/s41598-023-40496-9), but in an implementation that differs from the [original GitHub implementation](https://github.com/biorack/blink/blob/main/blink/matrix_manipulation.py).

In terms of runtime both implementations are close. The original seems to still be a bit faster, but I considered that to not be worth spending too much time on (at least not to me right now).
<img width="1715" height="1295" alt="image" src="https://github.com/user-attachments/assets/23a89669-442c-4a72-87ec-d1f412c9cacb" />

One consequence of the different implementation is that the rounding is not the same for the tolerance windows. The original BLINK, say with a tolerance of `0.01` was an approximation of the `CosineGreedy` with tolerance < 0.01 (which is why the authors used `tolerance=0.0099`. The implementation in this PR, however, sticks to the same tolerance so it would approximate CosineGreedy with a `tolerance=0.01`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5c0dafc7a3b5`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.