# Issue

**Title:** Feature/add parquet

## Description

Add functions/methods to import and export spectra from/to `.parquet`-files.
I here also decided to add `pyarrow` to the default dependencies since this is now the default option in Pandas >= 3.0 as well. But this could in principle also be made an optional dependency if this is considered too heavy.

The parquet import/export is now mostly made for the `SpectraCollection` API to really use the full benefits of this format.
```python
from matchms.importing import load_from_parquet

collection = load_from_parquet(file_path)
```

Further options are to select specific columns, and to filter based on column values.

This will close #1001

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a2fbc0148c1e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.