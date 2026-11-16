# Issue

**Title:** feat(g2p): add gget g2p module for the Genomics 2 Proteins portal

## Description

## Summary

. Adds a new module **`gget g2p`** that queries the [Genomics 2 Proteins (G2P) portal](https://g2p.broadinstitute.org/) (Broad Institute; Kwon, Safer, Nguyen et al., *Nature Methods* 2024) to link genes/proteins to residue-level structural and functional annotations.

The G2P REST API serves **tab-separated values**, which the module parses into a pandas DataFrame — fitting gget's "query a database → DataFrame in one line" idiom (cf. `gget pdb`, `gget bgee`).

## What it does

`gget.g2p(gene, uniprot_id, resource="features"|"map"|"alignment", isoform=None, save=False, verbose=True)`

- **`features`** (default): per-residue feature table (AlphaFold pLDDT, UniProt sites, secondary structure, predicted pockets, PTMs, …) — 140+ columns.
- **`map`**: gene → transcript → protein isoform → structure map (UniProt / Ensembl / RefSeq / PDB identifiers).
- **`alignment`**: residue-level sequence alignment between two isoforms (requires `isoform`; `uniprot_id` is the canonical isoform).

```bash
gget g2p BRCA1 -u P38398                 # per-residue features (JSON)
gget g2p BRCA1 -u P38398 -r map --csv    # isoform/structure map (CSV)
gget g2p LDLR -u P01130-1 -r alignment -i P01130-2
```

## Changes
- `gget/gget_g2p.py` — new module (direct REST via `requests`, TSV → DataFrame; no new heavy dependency, does not vendor the `g2papi` client).
- `gget/main.py` — `parser_g2p` + dispatch (positional `gene`, `-u/--uniprot_id`, `-r/--resource`, `-i/--isoform`, `-o/--out`, `-csv`, `-q`).
- `gget/__init__.py` — export `g2p`; `gget/constants.py` — `G2P_API`.
- `tests/test_g2p.py` — live integration tests (assert on stable columns / identifiers, since the feature table is wide and its values can change) + network-free argument-validation tests.
- `docs/src/en/g2p.md` + `docs/src/en/updates.md`.

## Testing
All tests pass locally (Python 3.11), and the CLI was exercised for all three resources:
```
$ pytest tests/test_g2p.py -v
...
6 passed
```

## Notes
- Endpoints/fields were confirmed against the **live** G2P API (the `g2papi` README suggested JSON, but the API actually returns TSV — verified and handled accordingly).
- `uniprot_id` is required; the help text and error message point users to `gget info` to find it. Auto-resolving UniProt IDs from a gene symbol could be a follow-up.
- Rate limits are undocumented; the module makes a single request per call.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `64a2ce7737f8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.