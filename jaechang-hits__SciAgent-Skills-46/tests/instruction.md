# Issue

**Title:** HL-419: [Agent][Skills] retrosynthesis 및 합성 경로 예측 기능 추가 (aizynthfinder)

## Description

Adds `aizynthfinder-retrosynthesis` — retrosynthetic route planning (CASP) with AiZynthFinder 4.4.1 from AstraZeneca Molecular AI. First retrosynthesis entry in the registry (`torchdrug` mentions it in passing; the new skill is cross-linked from its When to Use).

| | |
|---|---|
| sub_type | `pipeline` (target SMILES → tree search → routes) |
| category | `structural-biology-drug-discovery` |
| license | `MIT` (AiZynthFinder's own) |
| size | 391 lines, 16 code blocks |

Scaffolded with `sciagent-skill-creator`, so frontmatter, path, and the registry entry are machine-generated.

## Contents

**Workflow (7 steps)** — `download_public_data` for models/stock → `config.yml` in v4 format (minimal + explicit) → SMILES validation with RDKit → MCTS tree search → `extract_statistics()` → route inspection and PNG rendering → `aizynthcli` batch screening with `--nproc`/`--checkpoint`.

**Recipes (4)** — one-step disconnections via `AiZynthExpander`; custom stock from a catalogue via `smiles2stock`; multi-policy (USPTO + RingBreaker) and disconnection-aware search with `break_bonds`; route re-ranking and rendering from a saved batch run.

**Key Concepts** — states the caveats that matter more than parameter tuning:
- the state score is a search heuristic, **not** a route-quality or confidence measure
- solve rate is dominated by the stock and template library, not the algorithm — an unsolved target means "not found under this stock, policy, and budget"
- no reaction conditions are predicted
- scorer catalogue, alternative search algorithms (Retro\*/breadth-first/DFPN), and an entry-point selection table

Key Parameters 12 rows, Troubleshooting 10 rows (v3→v4 config migration, InChIKey-vs-SMILES stock files, `template_column` mismatch, missing `build_routes()`, onnxruntime-not-TensorFlow).

## Verification

Every API surface was checked against the v4 source on GitHub rather than trusted from the draft — the published docs pages still show v3 paths in places:

| Claim | Source checked |
|---|---|
| 4.4.1, Python 3.10–3.12, MIT | PyPI JSON |
| 6 downloaded files + generated `config.yml` | `tools/download_public_data.py` |
| `Scorer` in `context.scoring.scorers_base` | `context/scoring/__init__.py` (docs page shows the v3 `scorers` path) |
| `RouteSelectionArguments(nmin, nmax, return_all)` | `analysis/utils.py` |
| `routes[i]["image"]`, `routes.reaction_trees` | `analysis/routes.py` |
| `tree_search() -> float` (elapsed seconds) | `aizynthfinder.py` |
| scorer access by name | `context/scoring/collection.py` |

Unverifiable field names (expander `metadata` columns) print `list(metadata.columns)` instead of being hardcoded.

## Test plan

- [x] `pixi run test` — 4223 passed
- [x] `pixi run validate` — 204 entries
- [ ] Live run against `download_public_data` output (needs the ~several-hundred-MB model/stock download; not executed here)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `48f77f2043a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.