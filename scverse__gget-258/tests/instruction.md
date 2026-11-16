# Issue

**Title:** feat(g2p): make g2p useful for variant-interpretation workflows + bug fixes

## Description

Hi @Elarwei001 — thanks for the original `gget g2p` module. While reviewing it for biological relevance we found that the wrapper faithfully exposed the three public G2P REST endpoints but didn't quite match how scientists actually use the portal day-to-day, and had a couple of silent-failure bugs against the live API. This PR closes that gap. Tagging you so you can sanity-check the scientific framing and naming.

## Why this PR exists (scientific motivation)

The G2P portal is fundamentally a **variant interpretation** resource — scientists land on it with a list of variants of interest (clinical screens, MAVE deep mutational scans, gnomAD outliers) and ask: *"at residue Y of protein Z, is this position in a folded region? at a pocket? at a PTM? does PFES flag it as enriched for pathogenic variants?"*

The previous `gget g2p` exposed the data needed to answer those questions but made the user do a lot of plumbing — look up the UniProt accession by hand, get all ~140 columns × N residues even when they only care about three positions, parse the comma-joined PDB string before feeding it into `gget pdb`, and figure out which of the 142 columns are actually the scientifically useful ones from the column headers alone. This PR is about closing that last mile so a working scientist can go from *"I have a list of variants"* to *"I have an annotated table"* in one call.

## What this PR does

### Scientific UX

- **Either `gene` or `--uniprot_id` is now sufficient** — the other is resolved via UniProt (cached). Gene → UniProt picks the canonical reviewed human Swiss-Prot entry; the resolution and its limitations (synonyms, paralogues, non-human, isoforms) are logged so users see what was chosen and how to override.
- **Invariant output schema.** The canonical pair used for the query is *always* prepended as `gene_name` / `uniprot_id` columns (and stored on `df.attrs`), so downstream code doesn't have to branch on which input mode the user used and the chosen identifiers survive in saved CSV/JSON files.
- **`residues=` filter** restricts `features` / `alignment` results to specific positions — Python accepts `int` / `list` / `range` / `set`; CLI accepts `--residues 185,1775,1812` or `100-200` or `1-50,185,300-310`. The whole point of fetching the features table is usually to score a small variant list; filtering client-side after fetch is one short line of pandas the user no longer has to write.
- **`map` results get a parsed `PDB Ids List` column** (`list[str]`) alongside the comma-joined `PDB Ids` string, so the output is directly chainable into `gget pdb` without `.split(",")` boilerplate.
- **Docs now advertise the columns that actually drive variant interpretation**: PFES (Protein Feature Enrichment Score) sub-scores, MaveDB per-residue functional scores, fpocket / af2bind / p2rank pocket predictions, intra/inter-chain interaction counts. Linked the [`g2p-bis`](https://github.com/broadinstitute/g2p-bis) feature-description repo so readers can decode the cryptic MaveDB column names.
- **Noted the upstream limitation** that variant overlays (gnomAD / ClinVar / HGMD) are web-portal-only — they aren't exposed by the public REST API and therefore aren't reachable from `gget g2p`. Setting honest expectations rather than implying parity.

### Bug fixes

- **Silent failure when the gene/UniProt pair was unknown.** The G2P portal returns HTTP 200 with a JSON body like `{\"status\":\"failure\",\"message\":\"No data for this gene.\"}` over the TSV channel. The previous code parsed that JSON string as a single TSV column header and returned a 0-row DataFrame with no error. Now detected, the upstream `message` is logged, and `None` is returned.
- **Consistent failure return.** All failure modes (network error, HTTP error, JSON error body, empty response, unresolvable identifier) now return `None`. Previously it was a mix of `None` and `pd.DataFrame()`, which forced callers to check both.
- **Retries** on transient failures (connection errors, read timeouts, HTTP 5xx) with exponential backoff — same pattern `gget bgee` / `gget opentargets` already use.
- **URL-encoding** of `gene` / `uniprot_id` / `isoform` path segments.
- **Removed dead `Accept` header** (the server ignores it and always returns `text/plain` regardless).

### API surface additions

- New `residues=` Python argument (and `--residues` CLI flag).
- New `out=` Python argument writes the result to an explicit CSV path; `save=True` continues to work and writes to the auto-named CSV in CWD; `out=` takes precedence when both are set.
- `alignment` now requires `uniprot_id` to be passed explicitly — gene→UniProt resolution returns the base accession and can't disambiguate isoforms.

### Backward compatibility

All existing call sites continue to work unchanged:
- CLI: `gget g2p BRCA1 -u P38398 -r features` ✓
- Python: `gget.g2p(\"BRCA1\", uniprot_id=\"P38398\", resource=\"features\")` ✓
- `save=True` behavior unchanged.

The one schema change is the two new leading `gene_name` / `uniprot_id` columns on every result, which we think is the right trade-off for invariant output across input modes.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `cb64a8e034bb`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.