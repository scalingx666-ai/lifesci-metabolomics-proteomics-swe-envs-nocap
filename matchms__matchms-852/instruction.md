# Issue

**Title:** Allow for other tools than `poetry`

## Description

Dear matchms team,

I recently tried to bump dependencies of matchms to support python 3.14 locally but it seems currently impossible because of `pynndescent`...

While doing so, I realized the current `pyproject.toml` contains `poetry`-specific markers which I rarely use.
Therefore, I tried to make it more generic and bump some dependencies that could be without managing to reach 3.14 but maybe soon?

Feel free to cherry pick anything useful! 😉

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `33704801aa19`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.