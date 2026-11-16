# Issue

**Title:** feat(alphafold): add custom jackhmmer save directory option

## Description

## Summary
[`gget alphafold`](alphafold.md): Added a new `jackhmmer_savedir` argument (`-jhd`/`--jackhmmer_savedir` on the command line) that lets you choose where the temporary jackhmmer files are stored. By default, `gget alphafold` still creates a `~/tmp/jackhmmer/` folder in your home directory (which can take up to ~2 GB of disk space); the new argument lets you redirect these files elsewhere, e.g. to a disk with more free space. Resolves .

## Testing
Unit tests in `tests/test_alphafold.py` (argument/path-handling level, since AlphaFold's heavy deps are unavailable in CI); run with pytest.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5506537f52e3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.