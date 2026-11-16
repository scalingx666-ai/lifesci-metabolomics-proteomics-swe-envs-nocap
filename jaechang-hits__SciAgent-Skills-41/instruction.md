# Issue

**Title:** feat: add rdkit-chemdraw-cdxml skill

## Description

## Summary

Adds a **Toolkit** skill for reading, writing, and editing ChemDraw **CDX/CDXML** files, under `structural-biology-drug-discovery`.

The skill is a **hybrid** of RDKit's `rdkit.Chem.rdChemDraw` (structure/reaction I/O + 2D depiction) and **direct CDXML XML editing** — because RDKit writes molecule structures only. Reaction arrows, plus signs, reaction schemes/steps, and free text/labels are ChemDraw canvas objects that must be built at the XML level.

### Files
- `skills/structural-biology-drug-discovery/rdkit-chemdraw-cdxml/SKILL.md` — 8 Core API modules (read mols, read reactions, write structures, good depiction, arrows, schemes/steps, text/labels, edit existing files), 3 end-to-end workflows, 11 best practices, 12-row troubleshooting
- `skills/.../rdkit-chemdraw-cdxml/references/cdxml-schema-reference.md` — element/attribute cheat-sheet (`n`/`b`/`arrow`/`graphic`/`step`/`scheme`/`t`/`s`/`fonttable`/`colortable`), coordinate conventions, enum tables, and a copy-paste document header
- `registry.yaml` — new entry (`sub_type: toolkit`)

## How it was verified

All API facts were confirmed empirically against RDKit 2026.03.4, not assumed:
- `rdChemDraw` function signatures via introspection; `HasChemDrawCDXSupport() == True`
- Real ChemDraw-authored CDXML markup (`<arrow>`, `<step>`, `<t><s>`) taken from RDKit's own test fixtures
- A hand-built reaction CDXML round-trips correctly through `ReactionsFromCDXMLBlock`

### Key pitfalls documented (from real good/bad generated examples)
- **RDKit `Mol` round-trip silently drops arrows and text** — editing a reaction must be done on the XML tree
- `rdChemDraw.MolToChemDrawBlock(..., CDX)` raises `UnicodeDecodeError`; use legacy `Chem.MolToCDXMLBlock(mol, CDXMLFormat.CDX)` for CDX bytes
- No redundant free-text atom labels on `Element` nodes (double-render bug)
- Uniform bond length across fragments; every reaction step needs a real arrow; subscript formulas via split `<s>` runs; XML escaping

## Test plan
- [x] `pixi run validate` — registry OK
- [x] `pixi run test` — full suite passes (4120 passed)
- [x] New code snippets execute and produce valid CDXML

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6eed456870df`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.