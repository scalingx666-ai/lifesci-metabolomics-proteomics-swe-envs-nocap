# Issue

**Title:** Implemented FASTA fetching, autoresolving sequence type for `SequenceOperator` searches

## Description

## Changes

* Implemented FASTA fetching logic from RCSB endpoint
* Added autoresolving of sequence for sequence searches (to make searching from FASTA files pain-free)

This effectively reimplements the `get_blast` functionality with the new API.
I also actually reimplemented `get_blast` with a deprecation warning.

Hypothetically, this should solve #26 

## Example Usage

Let's say I want to find any structures that are similar in sequence to the first polymer sequence in 6TML's FASTA file.
I would do so using the following code:

```python
from pypdb.clients.fasta.fasta_client import get_fasta_from_rcsb_entry
from pypdb.clients.search.search_client import perform_search
from pypdb.clients.search.search_client import SearchService, ReturnType
from pypdb.clients.search.operators.sequence_operators import SequenceOperator

# Fetches FASTA results from RCSB, as a list of `FastaSequence` objects.
fasta_sequence_list = get_fasta_from_rcsb_entry("6TML")
# Let's arbitrarily pick the first element in the list to search with
sequence_of_interest = fasta_sequence_list[0].sequence

# Performs sequence search ('BLAST'-like) using the FASTA sequence
results = perform_search(
    search_service=SearchService.SEQUENCE,
    return_type=ReturnType.ENTRY,
    search_operator=SequenceOperator(
        sequence=sequence_of_interest,
        identity_cutoff=0.99,
        evalue_cutoff=1000
        # note that the search SequenceType is autoresolved (this fails with ambiguous sequences like "AAAAA")
      ),
    return_with_scores=True
)

results
>>> [ScoredResult(entity_id='6TMK', score=1.0), ScoredResult(entity_id='6TML', score=1.0), ScoredResult(entity_id='6TMJ', score=1.0), ScoredResult(entity_id='6TMG', score=1.0)]
```

## Tests + `mypy`

Tests pass with `pytest`.
Typechecking passes with `mypy --namespace-packages pypdb/path/to/file.py` for all files changed.

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `4b58f377104c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.