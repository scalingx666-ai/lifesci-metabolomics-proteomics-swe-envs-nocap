# Issue

**Title:** Add spectra collection

## Description

First draft of a SpectraCollection as discussed in #869, #873 and #688 when working with multiple Spectra.
This encapsulates Fragments (as csr_array) and Metadata (as DataFrame) and enables:
* faster peak processing due to sparse implementation
* synchronized Fragment and ;etadata access (e.g., removing/filtering Spectra will remove both Fragment and Metadata entry)
* sorting over either Fragment attributes (e.g., intensity sum) or Metadata keyword entries/columns
* filtering of many Spectra using masks for Fragment attributes or Metadata entries
* computing Spectra hashes and remove duplicates
* displaying minimal Fragment statistics (Peak counts, Intensity Sums and Shannon Entropy based on Intensities)
* Pandas-like logic for filtering, sorting and inplace Operations and slicing

### Working with SpectraCollection:
```
spectra = list(load_from_mgf("..."))
spec_coll = SpectraCollection(spectra)

sliced_spectra = spec_coll[:10]
...
```

### Sorting
SpectraCollection can be sorted based on Fragment attributes:
`spec_coll.sort(by="sum", on="fragments")`
or by Metadata:
`spec_coll.sort(by="retention_time", on="metadata", inplace=False)`

### Filtering
SpectraCollection can be filtered based on MetaData entries:
`spec_coll.filter(coll.metadata["ms_level"] == 2)`
By Fragment attributes:
`spec_coll.filter(coll.fragments.sum() > 500)`
or by boolean masks
```
mask = [True, False, ...]
spec_coll.filter(mask)
```

Still TBD:

- [ ] Advanced filtering pipeline/interface to filter many Spectra efficiently
- [ ] Adjust Importing Spectra to directly import into SpectraCollection (right now SpectraCollection gets a list of Spectrum Objects)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1c60d8e4c90d`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.