# Issue

**Title:** Making entropy less entropic, in a good way!

## Description

This PR fixes correctness and parity issues in FlashSimilarity spectral entropy scoring, and tightens test/dep stability around ms_entropy.

## What this PR fixes

1. Fragment entropy matching now uses one-to-one peak matching per spectrum pair.
2. Zero/negative intensity peaks no longer consume one-to-one matches.
3. Fragment mode now first narrows to candidate library spectra before pairwise scoring (avoids full per-row all-spectrum scans).
4. Entropy weighting in flash utils now uses natural-log entropy (aligned with ms_entropy behavior).
5. Dev dependency on ms_entropy is pinned to a stable compatibility range: >=1.4.0,<1.5.

## Implementation details

- Added spectrum-major per-spectrum peak storage in the library index (spec_offsets, spec_mz, spec_int) to support efficient one-to-one pairwise scoring.
- Reworked fragment entropy row scoring to:
  - gather candidate columns from global sorted peaks,
  - run one-to-one two-pointer matching only on those columns.
- Updated entropy weighting internals to use np.log(...)-based entropy, while previously was using log2.
- Added/updated tests to lock behavior.

## Tests added/updated

- Regression: overlapping windows remain bounded in fragment entropy scoring.
- Regression: non-positive peaks do not break valid one-to-one matches.
- Matrix vs pair consistency with sparse candidate columns.
- New parity suite against ms_entropy on reference spectra for:
  - Da tolerance path,
  - PPM tolerance path,
  - both pair() and matrix() outputs.
- Updated flash utils tests for new index fields and entropy-weighting semantics.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9f27ba89d8c4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.