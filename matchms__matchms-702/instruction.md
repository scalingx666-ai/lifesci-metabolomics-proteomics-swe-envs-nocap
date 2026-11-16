# Issue

**Title:** IndexError in `.matrix` when all scores are 0

## Description

Using .matrix of any similarity, when none of the scores are > 0, gets us an index error. Specifically:

```py

from matchms.similarity import CosineGreedy
from ..builder_Spectrum import SpectrumBuilder

builder = SpectrumBuilder()
spectrum_1 = builder.with_mz(np.array([100, 200, 300], dtype="float")).with_intensities(
    np.array([0.1, 0.2, 1.0], dtype="float")).build()

spectrum_2 = builder.with_mz(np.array([50, 60, 70], dtype="float")).with_intensities(
    np.array([0.5, 0.2, 1.0], dtype="float")).build()

scores = CosineGreedy().matrix([spectrum_1], [spectrum_2]) # IndexError
```

Will give an index error. This PR adds testcase, and a fix for this.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `df27f3089014`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.