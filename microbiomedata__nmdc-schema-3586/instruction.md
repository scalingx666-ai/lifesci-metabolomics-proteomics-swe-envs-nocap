# Issue

**Title:** Add NovaSeq X Plus PV to `InstrumentModelEnum`

## Description

In this PR, we are adding a PV for "Illumina NovaSeq X Plus".

Previously, we had just captured that as an alias of "Illumina NovaSeq X" but after looking through the model specifications from Illumina here: https://www.illumina.com/systems/sequencing-platforms/novaseq-x-plus/specifications.html we can see that they are two different models.

OBI captures them as two terms too. See https://www.ebi.ac.uk/ols4/ontologies/obi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FOBI_0003685?lang=en

<img width="517" height="319" alt="image" src="https://github.com/user-attachments/assets/b6bde44d-6988-4256-bb96-e069226d3d4e" />

So we are removing "Illumina NovaSeq X Plus" as an alias from "novaseq_x", making it it's own PV and also adding mappings to the right OBI terms.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a7f2dfaec37c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.