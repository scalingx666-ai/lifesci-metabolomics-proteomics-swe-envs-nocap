# Issue

**Title:** Data module

## Description

I wrote most of the data fetching module, trying to follow the coding styles and structures of the other submodules in `clients`. 

Briefly:

- created a `DataFetcher` class to allow the user to add the type of data (`DataTypes` class) and its properties to fetch.
- `clients/data/EXAMPLES.md` summarize the new functionality
- the appropriate tests are in `clients/data/test_data_types.py`
- Added the option to return fetched data as a Pandas dataframe. This necessitated adding a `pandas` requirement in `setup.py`.  

What's missing:
- `mock`s in tests. Currently, the unit tests just fetch data from the PDB and check if the relevant fields are populated.
- The following data types: `PubMed Integrated Data`, `UniProt Integrated Data`, `DrugBank Integrated Data`
- some sort of a mechanism that would prevent the user from doing large batch requests (see https://data.rcsb.org/#gql-usage-guidelines), mostly because it's not immediately clear to me what would constitute a large request
- some sort of a caching mechanism to prevent the fetching of already existing information. This could be done by checking what's in the memory, or, perhaps by caching stuff on the disk. I'm not sure which one is more reasonable.
- the examples live solely in `EXAMPLES.md` and have not yet been copied to `demos.ipynb`.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3ef016c7c95f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.