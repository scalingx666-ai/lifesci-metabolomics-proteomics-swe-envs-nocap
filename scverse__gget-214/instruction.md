# Issue

**Title:** feat(cellxgene): add support for non-human primate species (macaca_mulatta, callithrix_jacchus, pan_troglodytes)

## Description

## Summary

CZ CELLxGENE Census LTS `2025-11-08` added three non-human primate species — rhesus macaque (`macaca_mulatta`), common marmoset (`callithrix_jacchus`), and chimpanzee (`pan_troglodytes`) — but `gget cellxgene` only exposed `homo_sapiens` and `mus_musculus`. This PR exposes the new organisms.

The underlying `cellxgene_census.get_anndata(organism=...)` already supports them, so the core query path is unchanged. This is an **additive, backward-compatible** change.

## Changes

- **`gget/gget_cellxgene.py`**
  - Add a `SUPPORTED_SPECIES` allowlist (the five organisms in the current Census).
  - Validate `species` early and raise a clear `ValueError` listing the valid options, instead of failing later inside the Census API call.
  - Update the `species` docstring.
- **`gget/main.py`**: update the CLI `--species` `choices` and help text. Previously `choices` rejected the new species at the argparse layer before the function ran.
- **Tests** (`tests/test_cellxgene.py` + `tests/fixtures/test_cellxgene.json`)
  - Network-free unit tests for the species validation (valid species accepted, unknown/typo species raise `ValueError`).
  - An integration test for `macaca_mulatta` (metadata query, `census_version="2025-11-08"`), following the style of the existing tests.
- **Docs**: `docs/src/en/cellxgene.md` and `docs/src/en/updates.md`. (Spanish docs are auto-generated and left untouched.)

## Testing

All cellxgene tests pass locally (Python 3.11):

```
$ pytest tests/test_cellxgene.py -v
...
6 passed
```

## Notes

- The new primate species require `census_version="2025-11-08"` (LTS) or newer. This is documented in the docstring, the CLI help, and the validation error message.
- Fully backward compatible: existing `homo_sapiens` / `mus_musculus` behavior is unchanged.
- Verified the `organism` keys against the live Census `2025-11-08`: `['callithrix_jacchus', 'homo_sapiens', 'macaca_mulatta', 'mus_musculus', 'pan_troglodytes']`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `5a65aadd621f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.