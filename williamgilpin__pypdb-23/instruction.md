# Issue

**Title:** [RCSB Search: Text Service] - Added full support

## Description

## Added Support for QueryGraph-Based Searches

[The new API](https://search.rcsb.org/index.html#building-search-request) allows for building up search queries based on boolean aggregation of various search query nodes. I did this through implementing `perform_search_through_graph`, within `search_client.py`.

### Example Question

For example, you can ask "I would like structures that are under 4 angstroms, and published after 2019 using CryoEM, and are either Homo sapiens or Mus musculus". 

### Example Syntax for Group Query
(this specific example asks for structures under 4 angstroms that are Homo sapiens or Mus musculus, but you can go as complicated as you like hypothetically).

I added this example to `EXAMPLES.md`.

```python
from pypdb.clients.search.search_client import QueryNode, QueryGroup, perform_search_with_graph
from pypdb.clients.search.search_client import LogicalOperator, ReturnType
from pypdb.clients.search.operators import text_operators

# QueryNode associated with structures with under 4 Angstroms of resolution
under_4A_resolution_operator = text_operators.ComparisonOperator(
       value=4,
       attribute="rcsb_entry_info.resolution_combined",
       comparison_type=text_operators.ComparisonType.GREATER)
under_4A_query_node = QueryNode(SearchService.TEXT,
                                  under_4A_resolution_operator)

# QueryNode associated with entities containing 'Mus musculus' lineage
is_mus_operator = text_operators.ExactMatchOperator(
            value="Mus musculus",
            attribute="rcsb_entity_source_organism.taxonomy_lineage.name")
is_mus_query_node = QueryNode(SearchService.TEXT, is_mus_operator)

# QueryNode associated with entities containing 'Homo sapiens' lineage
is_human_operator = text_operators.ExactMatchOperator(
            value="Homo sapiens",
            attribute="rcsb_entity_source_organism.taxonomy_lineage.name")
is_human_query_node = QueryNode(SearchService.TEXT, is_human_operator)

# QueryGroup associated with being either human or `Mus musculus`
is_human_or_mus_group = QueryGroup(
    queries = [is_mus_query_node, is_human_query_node],
    logical_operator = LogicalOperator.OR
)

# QueryGroup associated with being ((Human OR Mus) AND (Under 4 Angstroms))
is_under_4A_and_human_or_mus_group = QueryGroup(
    queries = [is_human_or_mus_group, under_4A_query_node],
    logical_operator = LogicalOperator.AND
)

return_type = ReturnType.ENTRY

results = perform_search_with_graph(
  query_object=is_under_4A_and_human_or_mus_group,
  return_type=return_type)
print(results) # Huzzah
```

## Bugfixes

Fixed bug in which you couldn't correctly query for structure resolution.
(due to needing to support integer QueryNode values).

## Tests + `mypy`

All tests pass, and all files pass `mypy` typing analysis.
(Done using: ` mypy --namespace-packages pypdb/clients/search/search_client_test.py` or another path)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `75612f9ef68f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.