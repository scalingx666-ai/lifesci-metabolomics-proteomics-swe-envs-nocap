# Issue

**Title:** Compact object headers, string deduplication

## Description

Tested on many libraries:
<img width="1069" height="283" alt="image" src="https://github.com/user-attachments/assets/3652c03d-9492-4863-8434-1b664700734d" />
<img width="1293" height="386" alt="image" src="https://github.com/user-attachments/assets/9b007d77-f624-4b34-975d-00c011e34827" />
Verdict: 672.8 MB reclaimed for ~10 s of background CPU on one thread and no pause

<img width="3746" height="638" alt="image" src="https://github.com/user-attachments/assets/d0f0889d-a405-442e-8d47-83d9c60f81cd" />

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `080180794212`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.