# Issue

**Title:** local-max: add gaussian smoothing option

## Description

Add gaussian smoothing option for local max mass detector

Savitzgy golay may introduce additional valleys which lead to false peaks:
<img width="1468" height="773" alt="image" src="https://github.com/user-attachments/assets/9b604e24-ecad-4822-b9db-b8455aebbe77" />

Gaussian does not:
<img width="1468" height="773" alt="image" src="https://github.com/user-attachments/assets/022ddc03-f66d-4f78-9232-b0228428d2e4" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7c45369b71d3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.