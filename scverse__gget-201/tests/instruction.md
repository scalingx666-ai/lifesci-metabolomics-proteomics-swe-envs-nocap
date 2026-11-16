# Issue

**Title:** Minor gget virus fixes

## Description

Main change:
- making sure a summary file is always produced

Minor fixes:
- [`gget virus`](virus.md): Bug fixes for edge cases, enhanced protein filtering, and UX improvements
  - Fixed missing `command_summary.txt` when API returns 0 records 
  - Improved date parsing error messages by passing filter names to `parse_date()` function
  - Reduced log noise: empty/missing collection dates now log at DEBUG level instead of WARNING
  - Added `annotated=False` option to filter for unannotated sequences (client-side filtering)
  - Improved protein filtering with better FASTA header parsing for segmented viruses (e.g., influenza)
    - Dynamically creates regex patterns for protein/segment matching
    - Better handling of complete protein annotations in header
  - Added progress bar to batched sequence downloads for improved user experience
  - Fixed cleanup of cached download files and directories to ensure identical output structure
  - Cleaned up logging messages for improved clarity
  -  Large datasets now stream to disk during fetch, preventing memory exhaustion on queries with 100,000+ records
  - Fixed incorrect field name mappings (camelCase → snake_case) to properly populate organism name, host, and collection date columns in CSV output
  - Added specific guidance when NCBI API returns transient server errors with numeric taxon IDs
  - Pagination loop now uses centralized `_retry_with_exponential_backoff()` helper function, reducing code duplication and improving maintainability

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `505bf21450d7`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.