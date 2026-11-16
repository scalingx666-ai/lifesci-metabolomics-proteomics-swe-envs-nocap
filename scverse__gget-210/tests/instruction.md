# Issue

**Title:** Virus extended features

## Description

## `gget virus` — Extended Features, Performance, and Resilience

### Summary

Major enhancement of the `gget virus` module adding new filtering capabilities, improved download resilience, memory optimization for large datasets, and better error recovery/reporting.

### Key Changes

**New Filters (GenBank-dependent)**
- `--provirus` — filter for/against proviral/integrated sequences
- `--isolate` — filter by isolate name
- `--genotype` — filter by genotype (e.g. H5N1, H3N2)
- `--isolation_source` — filter by tissue/specimen source
- `--env_source` — filter by environmental source (mutually exclusive with `--host`)
- `--gen_mol_type` — filter by genomic molecule type
- `--submitter_name` / `--submitter_institution` — filter by submitter metadata
- Auto-enables `-g` (GenBank metadata retrieval) when any GenBank-dependent filter is used

**Performance & Resilience**
- Switch to EPost+EFetch History Server pipeline for large sequence downloads (NCBI-recommended approach)
- API key support (`--api_key` / `NCBI_API_KEY` env var) for 10 req/sec vs 3 req/sec rate limits
- Improved retry/backoff: 15 retries with capped exponential delay, finer-grained page-size fallback
- Retry logic extended to POST-based downloads
- Streaming FASTA filtering to disk (avoids loading all sequences into memory)
- Chunked CSV output for large metadata sets
- Garbage collection and tightened memory management to avoid leakage
- Memory monitoring between processing stages

**Checkpoint/Resume** [ #204 ]
- `--baseline` — deduplicate against previous run's metadata to skip already-downloaded accessions
- `--merge-results` / `--no-merge` — control whether new results merge with baseline
- Partial metadata saved on API failure with recovery command in summary

**Command Summary Enhancements**
- Wall-clock runtime reporting
- Memory usage reporting
- Per-stage filter statistics (metadata filter, GenBank filter, sequence filter)
- Failed operation details with retry URLs and recovery instructions

**Date Handling**
- Support for date ranges like `2020/2021` in collection/release date filters

**Updated Binaries**
- NCBI `datasets` CLI updated to v18.28.0

**Other Improvements**
- Early GenBank metadata pre-filtering before sequence download (reduces download volume)
- Retry with `skip_cache` fallback when optimized cached strategies fail
- Improved handling of all-virus queries given current API limitations
- Better `fetch_virus_metadata` fallback logic for empty first pages
- Improved warning messages and code comments

### Testing
- Tested with HIV-1, SARS-CoV-2, and Influenza A queries
- New unit tests cover baseline parsing, GenBank filtering, new CLI args, date range handling, and error recovery

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `ee21c507e92b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.