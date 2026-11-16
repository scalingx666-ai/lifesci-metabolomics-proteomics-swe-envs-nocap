# Issue

**Title:** Unpin ProDy by handling pathlib to string casting

## Description

Given the big deprecation issues that were addressed in [latest ProDy releases](https://github.com/prody/ProDy/releases)  (imports from `collections` and `BioPython`), it would be nice to upgrade the ProDy installation to >2.0.1 in lightdock.

Related lightdock issue was originally reported in #29, but the current workaround is a pin at 2.0.1.

The pin was needed after ProDy introduced [string-specific methods](https://github.com/prody/ProDy/blob/af92048974457c678b0a2e9fd23e9aa1f87aa491/prody/proteins/pdbfile.py#L231) to `parsePDB` in >=2.0.2, which will raise `AttributeError: 'PosixPath' object has no attribute 'endswith'` , primarily in these blocks:
* https://github.com/lightdock/lightdock/blob/edbbd363def9f5866fb27c502069fe19610303e5/lightdock/prep/starting_points.py#L120-L121
* https://github.com/lightdock/lightdock/blob/edbbd363def9f5866fb27c502069fe19610303e5/bin/lgd_cluster_bsas.py#L37-L39
* 
https://github.com/lightdock/lightdock/blob/edbbd363def9f5866fb27c502069fe19610303e5/lightdock/structure/nm.py#L25

Now that lightdock supports PosixPath objects, we should consider type-casting `PosixPath` to `str` before piping to to `parsePDB`, at least until ProDy develops proper support for pathlib.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `edbbd363def9`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.