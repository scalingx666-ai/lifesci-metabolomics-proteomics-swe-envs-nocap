# Issue

**Title:** feat: add molecular-visualization-3dmol skill

## Description

## Summary

Adds a reusable **Toolkit** skill `molecular-visualization-3dmol` under `data-visualization`: emit **self-contained 3Dmol.js HTML viewers** for molecular structures, trajectories, and vibrational modes — no server, no build step, no Python runtime to view.

Split out of `neb-irc-activation-energy` so any skill can reuse it (that skill produces the TS imaginary-mode and IRC trajectories this one animates).

## What's included

```
skills/data-visualization/molecular-visualization-3dmol/
├── SKILL.md                 # Toolkit: 6 Core API modules, 3 workflows
└── scripts/mol_viewer.py    # one-call HTML generator (static / trajectory / vibrate)
```

- **`scripts/mol_viewer.py`** — generates a standalone viewer from `.xyz/.trj/.pdb/.sdf/.mol2/.cube`. Animated modes get a **play/pause button and a speed slider bound to `interval` (ms)** — never the frame-skip `step`, which is the usual cause of "too fast"/jumpy playback. Coordinates are embedded via `json.dumps` so quotes/newlines in the data can't break the JS.
- **Two vibrational-mode paths**: precomputed frame trajectory (`addModelsAsFrames`) or per-atom `dx/dy/dz` vectors via 3Dmol's `vibrate()`.
- **Core API** (6 modules): viewer + load, styles/coloring, trajectory animation, `vibrate()` normal modes, surfaces + `.cube` isosurfaces, labels + speed control.
- **Workflows**: TS imaginary-mode animation, MD/IRC playback, protein–ligand docking pose.
- **Key Concepts**: `interval` vs `step`, coordinates-are-strings, CDN/CSP caveats.

## Test plan

- [x] `pixi run test` — full suite passes (4143), including the toolkit structural checks (Core API modules, code-block count, Common Workflows, Key Parameters/Troubleshooting rows) and registry integrity.
- [x] `mol_viewer.py` verified on fixtures for all three modes: `static` (`addModel`), `trajectory` (`addModelsAsFrames` + `animate`), `vibrate` (`vibrate()` + `animate`), each emitting valid standalone HTML.
- [x] Script syntax-checked (`ast.parse`).

## Notes

- The viewer loads 3Dmol.js from a CDN, so opening the HTML needs network access; documented in Prerequisites/Troubleshooting.
- Independent of PR #44 (`neb-irc-activation-energy`); the two cross-reference each other in Related Skills. A follow-up can slim `neb-irc`'s `make_visuals.py` to delegate its HTML generation here once both land.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `98f41e63465e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.