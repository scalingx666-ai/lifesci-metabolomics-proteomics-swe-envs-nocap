# Issue

**Title:** Implemented Sequence and Structure RCSB Search Services

## Description

## Implemented Features

1. Searching by sequence (BLAST-like)
2. Returning scores with results
3. Specifying pagination and sorting options using "request_options"
4. Implemented Structural Search using Biozernecke.

This should close out #18 and #26.

## Example Usage of Sequence
```python
from pypdb.clients.search.search_client import perform_search, RequestOptions
from pypdb.clients.search.search_client import SearchService, ReturnType
from pypdb.clients.search.operators.sequence_operators import SequenceOperator
from pypdb.clients.search.operators.sequence_operators import SequenceType

results = perform_search(
    search_service=SearchService.SEQUENCE,
    return_type=ReturnType.ENTRY,
    search_operator=SequenceOperator(
        sequence_type=SequenceType.PROTEIN,
        sequence=(
          "SMVNSFSGYLKLTDNVYIKNADIVEEAKKVKPTVVVNAANVYLKHGGGVAGALNKATNNAMQVESDDY"
          "IATNGPLKVGGSCVLSGHNLAKHCLHVVGPNVNKGEDIQLLKSAYENFNQHEVLLAPLLSAGIFGADP"
          "IHSLRVCVDTVRTNVYLAVFDKNLYDKLVSSFL"),
        identity_cutoff=0.99,
        evalue_cutoff=1000
      ),
    return_with_scores=True,
    request_options = RequestOptions(
        result_start_index=42,
        num_results=100,
        sort_by="score",
        desc=True)
)
```

This yields:
```python
[ScoredResult(entity_id='5RV6', score=1.0), ScoredResult(entity_id='5RUT', score=1.0), ScoredResult(entity_id='5RV5', score=1.0), ScoredResult(entity_id='5RV8', score=1.0), ScoredResult(entity_id='5RUW', score=1.0), ScoredResult(entity_id='5RV7', score=1.0), ScoredResult(entity_id='5RUV', score=1.0), ScoredResult(entity_id='5RUI', score=1.0), ScoredResult(entity_id='7KQO', score=1.0), ScoredResult(entity_id='5RUH', score=1.0), ScoredResult(entity_id='7KQP', score=1.0), ScoredResult(entity_id='5RUK', score=1.0),
...
etc.
...
```

## Example Usage of Structure

Note that "1CLL" corresponds to a Calmodulin structure bound to Ca2+.

Also, searching for `rcsb_chem_comp_container_identifiers.comp_id` with
an exact match to `"CA"` yields only structures in complex with Ca2+
(filtering out structures in complex with other metals like strontium).

```python
from pypdb.clients.search.search_client import perform_search_with_graph
from pypdb.clients.search.search_client import SearchService, ReturnType
from pypdb.clients.search.search_client import QueryNode, QueryGroup, LogicalOperator
from pypdb.clients.search.operators import text_operators, structure_operators

is_similar_to_1CLL = QueryNode(
  search_service=SearchService.STRUCTURE,
  search_operator=structure_operators.StructureOperator(
      pdb_entry_id="1CLL",
      assembly_id=1,
      search_mode=structure_operators.StructureSearchMode.STRICT_SHAPE_MATCH
  )
)

is_in_complex_with_calcium = QueryNode(
  search_service=SearchService.TEXT,
  search_operator=text_operators.ExactMatchOperator(
    attribute="rcsb_chem_comp_container_identifiers.comp_id",
    value="CA"
  )
)

results = perform_search_with_graph(
  query_object=QueryGroup(
    logical_operator=LogicalOperator.AND,
    queries=[is_similar_to_1CLL, is_in_complex_with_calcium]
  ),
  return_type=ReturnType.ENTRY
)
```

## Testing 
Tests passed using `pytest`

Typing passed using `mypy --namespace-packages pypdb/path/to/file.py`

## Miscellaneous Notes

Apologies for the large commit! In future I'll be better about using branches.

Happy holidays!

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9f288c89ac7f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.