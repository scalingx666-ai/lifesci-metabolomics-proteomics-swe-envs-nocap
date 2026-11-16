# Issue

**Title:** Dev -> main

## Description

**Version ≥ 0.30.1** (Feb 08, 2026):  
- [`gget virus`](virus.md): Metadata streaming optimization, improved protein filtering, and enhanced error handling and retry logic
  - Metadata now streams to disk during fetch to prevent memory exhaustion on large datasets (100,000+ records)
  - Fixed metadata CSV mapping (camelCase → snake_case) for organism name, host, and collection date
  - Enhanced protein filtering for segmented viruses with improved FASTA header parsing
  - Added `annotated=False` option for filtering unannotated sequences
  - Added progress bars to batched sequence downloads
  - Fixed collection date naming bug
  - Improved error messages for invalid filter dates
  - Added enhanced retry attempts for virus name resolution
  - Added verbosity to influenza A and COVID-19 checking steps

with @ferbsx

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `b55bff8368bc`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.