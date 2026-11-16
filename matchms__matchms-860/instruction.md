# Issue

**Title:** Calling Ghostbusters on phantom pairs

## Description

`CosineHungarian` builds a cost matrix initialised to `1.0` and overwrites cells where a real within-tolerance peak pair exists with `1 - intensity_product`. When `scipy.optimize.linear_sum_assignment` solves this matrix, it assigns exactly `min(rows, cols)` pairs. If a peak has no valid partner left, the algorithm assigns it to a cell still at `1.0` — a phantom pair.

**Before this fix**, `used_matches` included every assignment, so phantoms inflated the match count. The score was unaffected because the formula `len(row_ind) - sum(costs)` naturally cancels phantom contributions (`1 - 1.0 = 0`).

**After this fix**, `used_matches` filters out assignments where `cost_matrix[x, y] >= 1.0` (i.e., no real within-tolerance pair existed). The score calculation continues to use all assignments, preserving correctness.

### Minimal example

```
Cost matrix (tolerance=2.0):

         R1(100)    R2(103)
L1(100)   0.9       1.0  (no pair: |100-103|=3 > tolerance)
L2(102)   0.0       0.5

Hungarian picks: L1->R2 (cost 1.0) + L2->R1 (cost 0.0) = total 1.0
                 (beats L1->R1 (0.9) + L2->R2 (0.5) = total 1.4)

L1->R2 is a phantom — those peaks are not within tolerance.

Old result: matches=2 (wrong)
New result: matches=1 (correct), score unchanged
```

*Sorry for the delay on this PR btw, I had it on my desktop for a year now but life happened.*

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0a069e3a4dc3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.