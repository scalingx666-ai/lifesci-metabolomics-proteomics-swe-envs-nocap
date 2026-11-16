# Issue

**Title:** Feature proposal: KEGG PATHWAY image generation

## Description

Hello.
Thank you very much for developing this useful software.

I would like to propose a feature in `gget enrichr` that produces a KEGG PATHWAY image with the genes from the enrichment analysis highlighted.

Example usage:

`gget enrichr -db pathway --kegg out.png --kegg_rank 1 DDX41 IRF3`

will output an image (`out.png`) with IRF3 highlighted in the rank 1 pathway.
The feature uses the library pykegg. It checks if the package is installed and raises an error if not.

I would be grateful if you could review the PR.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `470c204e9fc1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.