# Issue

**Title:** Add Flash index object

## Description

This pull request introduces support for persistent, reusable indices for fast (Flash) similarity search in `matchms`, with new APIs for building, saving, loading, and searching against these indices. This enables more efficient repeated searches against large spectral libraries, and provides a robust serialization format for indices. The changes affect both the `Cosine` and `Entropy` similarity classes, and add a new `FlashIndex` class to encapsulate the persistent index logic.

**Persistent Flash Index Support**

* Added a new `FlashIndex` class in `flash_index.py` that encapsulates a reusable, serializable index for SpectraCollection-native Flash search, including methods for saving and loading indices as non-pickle `.npz` files with metadata and validation.
* Updated both `Cosine` and `Entropy` similarity classes to add methods for building (`build_index`), saving (`save_index`), loading (`load_index`), and searching (`search`) with persistent `FlashIndex` objects. This enables efficient repeated searches without rebuilding the index.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `622fcbb9578b`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.