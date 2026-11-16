# Issue

**Title:** feat: add neb-irc-activation-energy pipeline skill

## Description

## Summary

Adds a new **Pipeline** skill `neb-irc-activation-energy` under `scientific-computing`: a NEB-IRC reaction activation-energy pipeline (reactant/product opt → CI-NEB → TS opt with Hessian → IRC verification → barrier reporting) using **GFN2-xTB via pysisyphus**. Adapted from a reference sandbox skill, reframed as a general-purpose pipeline with feasibility/sizing moved to `references/`.

The skill was hardened against real execution-trace failure modes and given two guaranteed visual deliverables.

## What's included

```
skills/scientific-computing/neb-irc-activation-energy/
├── SKILL.md                       # Pipeline sub-type, 6 workflow steps
├── scripts/
│   ├── setup_env.sh               # conda-free xtb (GitHub release) + pysisyphus (PyPI)
│   ├── pipeline.yaml              # preopt→IDPP→CI-NEB→TSopt(Hessian)→IRC→endopt
│   ├── check_result.py            # 3-gate verification (exit 0 = all pass); prints ΔE‡/ΔE_rxn
│   └── make_visuals.py            # builds the two deliverables in one call
└── references/
    ├── feasibility.md             # measured timings, atom-count sizing, DFT limits
    └── energetics.md              # ΔE‡/ΔH‡/ΔG‡ definitions, thermochemistry, reporting
```

## Two visual deliverables (`make_visuals.py`)

- **`irc_energy_profile.png`** — IRC step vs relative energy, TS marked, kcal/kJ dual axis. Energies recomputed per IRC frame via xtb single points (the `*_irc.trj` comment lines carry no energy), at the pipeline's exact level auto-read from `pipeline.yaml`.
- **`ts_imaginary_mode.html`** — 3Dmol.js animation of `ts_imaginary_mode_000.trj` (written by `tsopt: do_hess`), with a play/pause button and a speed slider so the playback is never too fast.

## Hardening (driven by SN2 F⁻ + CH₃Cl execution traces)

- **Bundled-script access**: materialize scripts into a local scratch dir via the leading-slash skill path + `read_file` (the agent had hit local-copy failure then a GitHub 404).
- **Local filesystem**: pysisyphus symlinks crash on mounted/s3fs dirs — run in `/tmp` and copy results back.
- **`setup_env.sh`**: guard `HOME` under `set -u`; robust pysisyphus version via `importlib.metadata`.
- **Thermochemistry consistency**: standalone `xtb --hess` must mirror pipeline charge/spin/solvent and use the optimized endpoint geometry, or ΔG‡ comes out nonsensical (often negative).
- **Barrier reporting**: `check_result.py` parses the endpoint-referenced `BARRIERS` block (ΔE‡, ΔE_rxn) instead of the TS-vs-first-COS-image number that understated ΔE‡.
- **Submerged-barrier trap** for ion + neutral documented across Key Concepts, `energetics.md`, and Troubleshooting.

SKILL.md was also tightened for concision (346 → 283 lines) by removing redundant/contradictory phrasing and unneeded examples.

## Test plan

- [x] `pixi run test` — full suite passes (4141 tests), including registry integrity, frontmatter, sub-type section/count checks.
- [x] `check_result.py` BARRIERS parsing verified against real pysisyphus output (107.84 / 10.19 kJ/mol).
- [x] `make_visuals.py` — pipeline.yaml auto-detection, frame parsing, IRC plot assembly (matplotlib render checked), and HTML generation verified on synthetic + real (14-atom / 21-frame) fixtures.
- [x] Scripts syntax-checked (`ast.parse`, `bash -n`).

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `55f9733a5ed5`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.