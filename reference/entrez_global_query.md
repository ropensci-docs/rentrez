# Find the number of records that match a given term across all NCBI Entrez databases

Find the number of records that match a given term across all NCBI
Entrez databases

## Usage

``` r
entrez_global_query(term, config = NULL, ...)
```

## Arguments

- term:

  the search term to use

- config:

  vector configuration options passed to httr::GET

- ...:

  additional arguments to add to the query

## Value

a named vector with counts for each a database

## See also

[`config`](https://httr.r-lib.org/reference/config.html) for available
configs

## Examples

``` r
if (FALSE) { # \dontrun{ 
NCBI_data_on_best_butterflies_ever <- entrez_global_query(term="Heliconius")
} # }
```
