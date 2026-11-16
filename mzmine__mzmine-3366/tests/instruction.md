# Issue

**Title:** tag potential duplicates in gap-filling

## Description

During gap filling it may happen that duplicate features are created for some files due to prior mis-alignment or inconsistencies in feature detection.
This introduces a tag to potentially falsely introduced features. It does not yet provide a cleanup, because i am currently unsure what the best way to do such a cleanup would be, as there may be multiple reasons for it happening in the first place.

<img width="1989" height="522" alt="image" src="https://github.com/user-attachments/assets/3c545547-8fc4-4aca-9548-c89c0fdd62d6" />


Equality is checked by the raw mz values, sicne the intensities may be smoothed. Only 50% have to match since the gap filling may be shorter or longer than the true peak.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `02e04e95c350`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.