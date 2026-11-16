# Issue

**Title:** expand topk implementation to Cosine

## Description

## Small Benchmarking Run
Before this PR (so current #1008):
| PR | Similarity | Method | n_jobs | Median search (s) | Result (MiB) | Peak RSS growth (MiB) |
|:--|:--|:--|--:|--:|--:|--:|
| #1008 | cosine | dense | 1 | 1.080 | 381.470 | 375.4 |
| #1008 | cosine | dense | -1 | 0.369 | 381.470 | 427.1 |
| #1008 | modified | dense | 1 | 4.645 | 381.470 | 466.0 |
| #1008 | modified | dense | -1 | 1.524 | 381.470 | 2,151.9 |


| PR | Similarity | Method | n_jobs | Median search (s) | Result (MiB) | Peak RSS growth (MiB) |
|:--|:--|:--|--:|--:|--:|--:|
| #1016 | cosine | topk | 1 | 6.826 | 0.771 | 0.2 |
| #1016 | cosine | topk | -1 | 1.092 | 0.771 | 101.0 |
| #1016 | modified | topk | 1 | 15.809 | 0.771 | 9.1 |
| #1016 | modified | topk | -1 | 2.246 | 0.771 | 206.3 |

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e007f4a59730`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.