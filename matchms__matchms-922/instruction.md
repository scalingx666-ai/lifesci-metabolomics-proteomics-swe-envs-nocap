# Issue

**Title:** Fix mzml loader

## Description

Solving #921 

The current mzml loader ignores all metadata that is not one of the 6 specified fields. 
It seemed somewhat easy to parse the data that the pyteomics reader, so that is my attempt here. 

Implemented the following:
1: mzml has hierarchical fields, this doesn't match well with matchms. So I wrote a script that flattens this hierarchy. It will just connect the different hierarchy levels with a "-". There are some cases where multiple entries are allowed. Like multiple precursor m/z, but these are (as far as I know) edge cases matchms doesn't support. 
2. Previously some parsing happened of converting to matchms key names. This happened in a separate method, now I moved it to the standard key conversions list, which also fits better with the general way this is handled in matchms.

So I think it still has all the old functionality now, with in addition the non standardized metadata keys also being loaded. 

@florian-huber What do you think. Do you know anyone that is familiar with using mzml files that could do a quick stress test? I now just tested on some files I had here and for those it worked fine. 

@hechth If I remember correctly, I think you worked with mzml files right? Would this work for you, or would this break your pipelines?

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f9cc919a5c5e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.