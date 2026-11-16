# Issue

**Title:** Add `ModifiedCosineLinear` from SIRIUS

## Description

This PR adds `ModifiedCosineLinear` implemented as a descendant of `CosineLinear`, the linear-time exact modified cosine that originated in SIRIUS.

It requires the same preprocessing of the non-modified variant where it merges close peaks first so that every peak has at most one direct and one precursor-shifted partner, finds both partner sets with a two-pointer sweep each, and then (and here is where the magic happens) **resolves the conflicts between them with a small dynamic program on the resulting paths**.

The bulk of the PR lines are from `tests/modified_cosine_linear_reference.json` fixture, generated from the https://github.com/earth-metabolome-initiative/mass-spectrometry-traits impl, which has been differentially fuzzed against the hungarian variant.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `48e09a28a883`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.