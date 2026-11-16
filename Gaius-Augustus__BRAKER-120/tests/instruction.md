# Issue

**Title:** Suggested fix to not mangle columns 1-8 in the output GTF (re: Issue #118)

## Description

Dr. Hoff,
Here is a suggested fix for issue #118 , which I have also encountered in a slightly different context:
Some of my input contigs have the suffix "_ctg#" (e.g. "Segkk117_quiver_pilon_ctg1"), so the regex substitution identified by visoca in #118 mangles these contig names in the output GTF (e.g. "Segkk117_quiver_pilon_ctm1-g1").  It's also possible that the regex matches/captures found in that MISSED1 and MISSED2 section of braker.pl match the contig name rather than the gene or transcript ID, so that would introduce another bug (perhaps indicated by visoca's followup comment).

The suggested fix simply splits the input line by tabs, and performs the regex matches/captures and substitutions on columns 9+ iteratively.  In testing on my own data, it no longer clobbers contig names in augustus.hints.gtf.

Hopefully this should remedy the issues faced by visoca, since it also addresses the regex capture that defines $g_id.

Best regards,
Patrick Reilly

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `036eb3b28fb3`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.