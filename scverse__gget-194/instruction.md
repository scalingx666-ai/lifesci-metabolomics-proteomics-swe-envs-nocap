# Issue

**Title:** Replace exec() with importlib.import_module()

## Description

## Summary
- Replaces unsafe `exec(f"import {import_name}")` with `importlib.import_module(import_name)`
- Adds `import importlib` to the imports

## Why
Using `exec()` with dynamic strings is a security concern and considered bad practice. While the current usage is limited to package names from a controlled set, `importlib.import_module()` is the proper way to dynamically import modules in Python.

## Test plan
- [ ] Run `gget setup alphafold` and verify it still works
- [ ] Run `gget setup elm` and verify it still works

🤖 Generated with [Claude Code](https://claude.com/claude-code)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `36148f8a599c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.