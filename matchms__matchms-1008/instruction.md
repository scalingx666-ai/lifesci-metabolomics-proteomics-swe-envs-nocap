# Issue

**Title:** Add memory efficient top-k search to Entropy index

## Description

This PR introduces **exact, memory-efficient top-k retrieval** for indexed spectral libraries, avoiding the allocation of dense query × reference score matrices when only the best matches are needed.

Supported similarity implementations:

- `**EntropySearch**` — optimized fragment-only entropy search.
- `**EntropyFlash**` **/** `**Entropy**` — fragment, neutral-loss, and hybrid entropy search.
- `**CosineFlash**` — standard cosine, neutral-loss cosine, and hybrid/modified cosine.
    

Existing dense search methods and compatible saved `FlashIndex` files remain supported.

## Key changes

- **Unified top-k API:** Added `search_topk()` and `search_prepared_topk()` with configurable `k`, `min_score`, `n_jobs`, and batching.
    
- **Compact results:** Introduced `TopKResults`, containing ranked reference indices, similarity scores, valid hit counts, and optional accepted peak-match counts for cosine.
- **Candidate-aware scoring:** Reusable worker-local buffers, epoch-based tracking, and touched-reference lists eliminate the need to initialize and scan full-library score rows for every query.
- **Exact matching:** Preserved entropy's fragment-first matching and cosine's greedy one-to-one assignment, including deterministic score ordering and tie-breaking.
- **Shared infrastructure:** Consolidated common Flash retrieval logic, worker scheduling, and candidate tracking while retaining separate numerical kernels for entropy and cosine.
- **Improved readability:** Refactored deeply nested scoring kernels into clearly named matching and finalization stages, improved variable naming, type hints, and NumPy-style docstrings.
    

Top-k output memory scales as **O(n_queries × k)** instead of **O(n_queries × n_references)**. Worker-local scratch memory still scales with library size.

## Example

```
results = similarity.search_topk(
    queries,
    library_index,
    k=100,
    min_score=0.1,
    n_jobs=-1,
)

reference_ids, scores = results.get_hits(0)
```

Cosine searches can additionally return accepted one-to-one peak-match counts using `get_hits_with_matches()`.

## Benchmark

To evaluate runtime and memory performance, a reproducible synthetic benchmark compares **dense search and top-k search** for Standard cosine (`CosineFlash`, fragment mode), Modified cosine (`CosineFlash`, hybrid mode), and Entropy (`EntropyFlash`, fragment mode). 

The benchmarking was done using 100k randomly generated reference and 1000 query spectra with 10 to 200 peaks in the 100 - 500 Da range, float32, tolerance = 0.01, topk = 100.

| Similarity | Method | n_jobs | Median search (s) | Result (MiB) | Peak RSS growth (MiB) |
|:--|:--|--:|--:|--:|--:|
| cosine | dense | 1 | 1.192 | 381.470 | 380.7 |
| cosine | dense | -1 | 0.344 | 381.470 | 426.6 |
| cosine | topk | 1 | 6.384 | 0.771 | 0.2 |
| cosine | topk | -1 | 0.935 | 0.771 | 99.5 |
| modified | dense | 1 | 4.181 | 381.470 | 466.3 |
| modified | dense | -1 | 1.562 | 381.470 | 2,147.2 |
| modified | topk | 1 | 14.910 | 0.771 | 10.9 |
| modified | topk | -1 | 2.227 | 0.771 | 201.5 |
| entropy | dense | 1 | 0.805 | 381.470 | 380.0 |
| entropy | dense | -1 | 0.237 | 381.470 | 385.7 |
| entropy | topk | 1 | 5.096 | 0.771 | 0.0 |
| entropy | topk | -1 | 0.781 | 0.771 | 68.8 |

While top-k scoring is slower for this synthetic workload, the substantial memory reduction makes searches against very large spectral libraries considerably more practical.

## Backward compatibility

- Existing `search()` and `matrix()` methods remain available.
- Existing compatible `FlashIndex` archives can be reused without migration.
- Numerical scoring and peak-assignment semantics are preserved.
- Top-k retrieval returns `TopKResults` rather than a truncated dense `Scores` matrix.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `2a3b6ced302f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.