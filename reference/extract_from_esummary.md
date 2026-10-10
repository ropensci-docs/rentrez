# Extract elements from a list of esummary records

Extract elements from a list of esummary records

## Usage

``` r
extract_from_esummary(esummaries, elements, simplify = TRUE)
```

## Arguments

- esummaries:

  Either an esummary or an esummary_list (as returned by
  entrez_summary).

- elements:

  the names of the element to extract

- simplify:

  logical, if possible return a vector

## Value

List or vector containing requested elements

## See also

[`entrez_summary`](https://docs.ropensci.org/rentrez/reference/entrez_summary.md)
for examples of this function in action.
