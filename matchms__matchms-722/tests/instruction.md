# Issue

**Title:** Save empty spectrum list as empty file

## Description

## Summary

No file is generated when `save_spectra` is called and the `spectra` parameter is an empty list, which can be unexpected behavior. This PR addresses that by generating an empty file and logging a warning. Completes #586.

## Changes

In `save_spectra`:

```python
if not isinstance(spectra, list):
    spectra = [spectra]

if len(spectra) == 0:
    logger.warning("No spectra to save. File will be empty.")
    open(file, "w").close()
    return
```

The diff is large because I reformatted the files in the `exporting` module (out of habit). I can revert these changes if desired.

## Testing

Ran the following code and confirmed that an empty file was created. Unit tests are passing on my machine.

```py
import matchms
spectra = []
matchms.exporting.save_spectra(
    spectra, file="spectra.json", export_style="json"
)
```

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1f904e0d469a`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.