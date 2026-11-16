# Issue

**Title:** Add 8cubedb module, CLI integration, docs, and tests

## Description

### **Summary**

This PR adds support for 8cubeDB  to the gget toolkit. [Link to 8cubeDB docs.](https://eightcubedb.onrender.com/docs)
Included are Python API functions, CLI subcommands, full documentation, and unit tests.

---

### **New Features**

#### **Python module: `gget_8cubedb`**

* `specificity()` – retrieves ψ and ζ specificity metrics
* `psi_block()` – retrieves ψ_block values
* `gene_expression()` – retrieves gene expression

#### **CLI**

Added via:

```
gget 8cubedb specificity …
gget 8cubedb psi_block …
gget 8cubedb expression …
```

#### **Tests**

* `tests/test_8cubedb.py`
* Hash-based outputs following gget patterns
* Fixture: `tests/fixtures/test_8cubedb.json`

#### **Docs**

* `docs/src/gget_8cubedb.md`
* gget 8cubedb added to Summary.md 
* Includes examples, CLI + Python usage, and citations

---

### **Notes**

* Fully black-formatted
* All tests pass
* No external dependencies added
* Compatible with existing CLI patterns

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c61cd6eee67`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.