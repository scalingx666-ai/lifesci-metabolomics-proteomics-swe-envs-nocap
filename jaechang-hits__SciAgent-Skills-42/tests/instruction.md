# Issue

**Title:** feat: cdxml scheme layout/typography polish + helper-copy fix

## Description

## Summary

Follow-up polish to `rdkit-chemdraw-cdxml`, driven by feedback on a rendered scheme (content crowded to the right, clipped reagent text, no sub/superscripts, `0 C`/`heat` instead of `0 °C`/`Δ`) and a script-not-found error in an agent run.

### `build_reaction_scheme.py`
- **Per-row heights** — each row is sized to its own tallest structure, not the global max, so rows of small molecules stop sitting in tall cells with a big empty band.
- **Spread a partial last row** across the full width (transition structure stays aligned under its vertical arrow) so it no longer leaves a column gaping empty.
- **Vertical-arrow conditions toward the page centre** so a long reagent name (`+ N-methylmaleimide`) no longer runs off the canvas edge.
- **Subscripts** for chemical formulas (`BH3`, `H2O2`, `C6H4…`) via `face=32`. Charges stay **inline** (`H+`, `OH-`) — Indigo renders a standalone `+` as a big reaction-plus and mangles superscript (`face=64`), and Arial has no Unicode sub/superscript glyphs, so a raised charge is not achievable in the preview.
- **`_symbolize`**: `"<n> C"` → `"<n> °C"`, the word `"heat"` → `"Δ"` (both render with the Arial font table).

### `check_scheme.py`
- Allow `°`, `Δ`, `∆` through the non-ASCII check (still flags other non-Latin-1 characters).

### `SKILL.md`
- **Fix the helper-copy instructions** (root cause of the agent's `ModuleNotFoundError`/`FileNotFoundError`): the `/SciAgent-Skills/...` path is reachable only via the read-file **tool**, not Python `open()`/`import`. Read each script with the tool, write it into the workdir, then import.
- Update Module 7 + Best Practice # 6 (°C/Δ render; charges inline; subscripts via `face=32`); add Troubleshooting rows for the copy error and the giant-`+` charge.

## Test plan

- [x] `pixi run test` — full suite passes (4120)
- [x] 5-step Diels-Alder scheme renders with `0 °C`, `Δ`, subscripted `BH3`/`H2O2`, inline `H+`, no clipped text, filled bottom-left; `check_scheme` reports 0 problems

Merge, then re-point the hyperlab-agent submodule bump (PR #421) to the new `SciAgent-Skills` main SHA.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7152b9d7a8c4`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.