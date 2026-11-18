# Issue

**Title:** post release: Escape literal dots in CURIE-prefix regex patterns

## Description

Escapes literal `.` characters in CURIE-prefix regexes that were matching any character (for example `insdc.sra:` also matched `insdcXsra:`). Brings these patterns in line with the same files' already-escaped ones (`img\.taxon`, `gnps\.task`, `emsl\.project`).

Escaped:
- `external_identifiers.yaml`: `insdc.sra` (4 slots), `mgnify.proj`, `jgi.proposal`, `jgi.analysis`
- `annotation.yaml`: `KEGG.REACTION`, `PANTHER.FAMILY` (on `has_function`)
- `nmdc.yaml`: `KEGG.ORTHOLOGY` (on `gene_function_id`)

Quoting matters: single-quoted scalars take `\.`, double-quoted take `\\.`.

Invalid examples added, each failing only on the now-literal dot, exercised by the CI examples step:
- `insdc.sra` (experiment), `mgnify.proj`, `jgi.proposal`, `KEGG.ORTHOLOGY` (gene_function_id), `KEGG.REACTION` and `PANTHER.FAMILY` (has_function)

No negative test for `jgi.analysis` (`jgi_portal_analysis_project_identifiers`) or `insdc.sra` runs (`insdc_analysis_identifiers`): both slots are defined but not attached to any class, so no example data can exercise them. The escapes still apply if those slots are later used. The orphan slots are a separate cleanup (; `insdc_analysis_identifiers` is also noted in #3198).

Escaping only tightens against malformed values; real data uses literal dots and still matches, so no migrator is needed.

Part of #3193. The CI detection check proposed there is left for a follow-up.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9e7c86de8ac5`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.