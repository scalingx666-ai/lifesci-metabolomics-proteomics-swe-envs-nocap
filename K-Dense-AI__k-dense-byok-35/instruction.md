# Issue

**Title:** Detect AMD GPUs in the host resource monitor

## Description

.

## Problem

The GPU probe in `server/src/system-stats.ts` only ever tried `nvidia-smi`, falling back to `ioreg` on Apple Silicon. An AMD card was invisible on every platform regardless of what was on `PATH` — `rocm-smi` was never invoked, so the reporter's `rocm-smi` install could not have helped.

## Change

- **Probe chain is now `nvidia-smi` → `amd-smi` (ROCm ≥ 6) → `rocm-smi` → `ioreg`.** First tool that answers wins, so a dual-vendor machine reports NVIDIA exactly as before.
- **Lenient AMD parsing, deliberately.** Both tools rename JSON fields between ROCm releases (`Card Series` → `Market Name`, bare numbers → `{value, unit}`) and answer `N/A` for counters a platform doesn't support. Keys are matched by substring, every field is independently optional, and the memory unit comes from whichever of the value object or the key's `(B)`/`(MB)` suffix states one. A rename costs one field, not the whole GPU.
- **No blank rows.** A tool that runs but reports nothing usable yields no GPU rather than a GPU with every field null.
- **UI: VRAM fallback.** The old condition hid the GPU row whenever utilization was null — which would have hidden the reporter's card even after detection worked, since ROCm on Windows commonly reports VRAM with no busy counter. The hover card now meters VRAM in that case and labels it `· no utilization counter`. The collapsed pill stays utilization-only; there is no room there to say which quantity it shows.
- **Docs.** `docs/basic-usage.md` gains a section on the monitor: the probe order, the VRAM-only case, and that the readout is display-only and never routes work to Modal.

## Tests

23 new tests in `server/test/system-stats-gpu.test.ts` over real output shapes: renamed product-name keys, `N/A` utilization, used-vs-total VRAM confusion, multi-card ordering (`card10` before `card0`), unit conversion, a warning banner ahead of the JSON, and the nvidia parser's existing behaviour.

Backend 616 pass, web 520 pass, both `tsc --noEmit` clean.

## Not verified

Whether ROCm 7.2 on Windows reports anything at all for an RDNA4 (9070 XT) card — no such hardware here. The parsers handle whatever comes back, but if that build reports neither utilization nor VRAM, no parsing change can help; the issue reply asks for raw tool output in that case.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c1ee553e122`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.