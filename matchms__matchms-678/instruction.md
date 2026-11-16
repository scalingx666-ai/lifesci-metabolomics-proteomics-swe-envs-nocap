# Issue

**Title:** fix name position

## Description

I had the problem with the plot_aigainst function that the labels were not at the correct place when setting min and max mz values , because it assumed the axis starts at 0.


![image](https://github.com/matchms/matchms/assets/43442120/b2343f3f-c7df-49e5-90c2-deafd97e83c1)


This very small fix makes it work by offsetting the labels to min_mz

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9282aa7388e1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.