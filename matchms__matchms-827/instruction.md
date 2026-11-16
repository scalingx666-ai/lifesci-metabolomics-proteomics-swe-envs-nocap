# Issue

**Title:** FlashSimilarity for faster flash entropy, cosine, modified cosine computation

## Description

New fast similarity score computation inspired by the Flash Entropy from Li and Fiehn (2023).

This is based on first creating a m/z index (`_LibraryIndex`) that contains ALL fragments of the dataset ordered by m/z. This allows much faster computation than, for instance, `CosineGreedy` or `ModifiedCosine`.

In the current implementation it is possible to chose differnt score types:
- `score_type` can be `spectral entropy` or `cosine`
- `matching_mode` can be `fragment`, `neutral_loss` or `hybrid` (hybrid being a combination of both fragments and neutral losses)

The computation of modified cosine scores is then a combination of `cosine` with `hybrid` matching mode.


I quickly compared `CosineGreedy` with `FlashSimilarity` (cosine mode) and blink ( ). This shows that FlashSimilarity is not scaling as well as Blink for the presented task (all-vs-all comparisons), but is MUCH faster than CosineGreedy, by about 100x. In addition, and unlike Blink, FlashSimilarity is no approximation but computes the exact same scores as CosineGreedy.

<img width="1051" height="1034" alt="image" src="https://github.com/user-attachments/assets/875faf4b-8c85-494c-9cc5-7ebe150d3aaa" />


`FlashSimlarity` now also allows to compute the modified cosine scores (exact same as with current `ModifiedCosine`) about 100x faster.
<img width="1067" height="1036" alt="image" src="https://github.com/user-attachments/assets/3125862f-9e0e-421b-bdfc-fcd0be120c8c" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c3e1c0f7b7ec`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.