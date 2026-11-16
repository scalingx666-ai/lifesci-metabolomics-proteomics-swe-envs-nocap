# Issue

**Title:** Fix filterGenemark.pl example to use --hints instead of --introns

## Description

The filterGenemark.pl script provides an example using a (nonexistent) `--introns` option: 
https://github.com/Gaius-Augustus/BRAKER/blob/21d749e9f2dd8b216a40ec45e963e27c4759d9bd/scripts/filterGenemark.pl#L102-L104
It apparently should be `--hints=hints.gff`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `21d749e9f2dd`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.