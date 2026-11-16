# Issue

**Title:** Keep valid SMILES shorter than four characters in repair_inchi_inchikey_smiles

## Description

.

`SpeciesString` accepted a SMILES only when it matched a character pattern of at least four characters. A valid short SMILES such as `CCO` (ethanol), `CO` (methanol) or `C=O` (formaldehyde) therefore got `target = None`, and `repair_inchi_inchikey_smiles`, which runs in `DERIVE_METADATA_IN_WRONG_FIELD` and so in the default filter sets, replaced it with `None`.

Change: strings shorter than the pattern length are accepted when `is_valid_smiles` (rdkit) parses them. Longer strings go through the existing pattern unchanged. Placeholders such as `NA`, `n/a`, `nan`, `-`, `0` or `?` are still rejected, since rdkit does not parse them.

Tests:
- `test_species_string.py`: short valid SMILES (`CCO`, `CO`, `CCN`, `C=O`, `C#N`, `C`, `O`) classified as `smiles`; short placeholders (`NA`, `nan`, `-`, `0`, `?`) still `None`.
- `test_repair_inchi_inchikey_smiles.py`: a spectrum with a short valid SMILES keeps it.
- `tests/filtering` and `tests/test_pipeline.py`: 1254 passed. `ruff check` and `ruff format --check` pass.

CHANGELOG entry under Fixed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `67f5a3701913`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.