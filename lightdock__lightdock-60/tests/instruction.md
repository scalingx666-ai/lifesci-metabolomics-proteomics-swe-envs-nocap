# Issue

**Title:** Add TOBI ADP-I and ADP-II scoring.

## Description

According to #55,TOBI's ADP scoring functions are implemented.

Their names are `tobia1` and `tobia2`.In CCharPPI,they are `AP_T1` and `AP_T2`.

Results between this branch and CCharPPI are as below.

Only 1r6q has significant difference.CCharPPI's `get_pots.py` has the same result,so there may be a mistake in the CCharPPI benchmark file.

![lightdock_tobi-2](https://github.com/lightdock/lightdock/assets/60164864/5cb644d5-c36e-4cba-86a1-950f20df213c)

![lightdock_tobi-1](https://github.com/lightdock/lightdock/assets/60164864/15322779-a8ed-4ed2-af5a-c53298a8bf2b)

I use `lgd_calculate_scoring.py` to calculate TOBI-ADP-I/II scores,without docking them by `lightdock3.py`.

Integration tests needed for this pull request.However,my laptop cannot complete this job.Poor CPUs.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a5a05d5717c3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.