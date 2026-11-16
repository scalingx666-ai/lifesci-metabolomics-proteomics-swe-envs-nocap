# Issue

**Title:** Remove unused Perl modules File::HomeDir and List::MoreUtils

## Description

braker.pl imports (but does not use) non-core Perl modules File::HomeDir and List::MoreUtils. This PR suggests removing their respective `use` statements to lighten the user-installed Perl module dependency burden a bit.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `0798591b7ad5`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.