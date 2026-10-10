# List databases available from the NCBI

Retrieves the names of databases available through the EUtils API

## Usage

``` r
entrez_dbs(config = NULL)
```

## Arguments

- config:

  config vector passed to
  [`httr::GET`](https://httr.r-lib.org/reference/GET.html)

## Value

character vector listing available dbs

## See also

Other einfo:
[`entrez_db_links()`](https://docs.ropensci.org/rentrez/reference/entrez_db_links.md),
[`entrez_db_searchable()`](https://docs.ropensci.org/rentrez/reference/entrez_db_searchable.md),
[`entrez_db_summary()`](https://docs.ropensci.org/rentrez/reference/entrez_db_summary.md),
[`entrez_info()`](https://docs.ropensci.org/rentrez/reference/entrez_info.md)

## Examples

``` r
if (FALSE) { # \dontrun{
entrez_dbs()
} # }
```
