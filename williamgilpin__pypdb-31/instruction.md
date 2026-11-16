# Issue

**Title:** [`get_pdb_file`] - Factored out `get_pdb_file` logic from `pypdb.py`.

## Description

## Change

* Factored out `get_pdb_file` function from `pypdb.py` to `pypdb/clients/pdb/pdb_client.py`.
* Left deprecated-warning function within `pypdb.py`.
* Added testing for all functionality in the function
* Fixed the function to work with compressed files (the trick was undoing the gz compression using `gzip`)

## Example Usage

```python
from pypdb.clients.pdb.pdb_client import PDBFileType, get_pdb_file

uncompressed_file_as_string = get_pdb_file("5JUP", PDBFileType.CIF, compression=True)
```

## Testing

Testing passes with `pytest`.
Mypy typechecking passes with the appropriate command.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `90179bba62b2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.