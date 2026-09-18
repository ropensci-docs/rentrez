# List available search fields for a given database

Fetch a list of search fields that can be used with a given database.
Fields can be used as part of the `term` argument to
[`entrez_search`](https://docs.ropensci.org/rentrez/reference/entrez_search.md)

## Usage

``` r
entrez_db_searchable(db, config = NULL)
```

## Arguments

- db:

  character, name of database to get search field from

- config:

  config vector passed to
  [`httr::GET`](https://httr.r-lib.org/reference/GET.html)

## Value

An eInfoSearch object (subclassed from list) summarizing
linked-databases. Can be coerced to a data-frame with `as.data.frame`.
Printing the object shows only the names of each available search field.

## See also

[`entrez_search`](https://docs.ropensci.org/rentrez/reference/entrez_search.md)

Other einfo:
[`entrez_db_links()`](https://docs.ropensci.org/rentrez/reference/entrez_db_links.md),
[`entrez_db_summary()`](https://docs.ropensci.org/rentrez/reference/entrez_db_summary.md),
[`entrez_dbs()`](https://docs.ropensci.org/rentrez/reference/entrez_dbs.md),
[`entrez_info()`](https://docs.ropensci.org/rentrez/reference/entrez_info.md)

## Examples

``` r
if (FALSE) { # \dontrun{
pmc_fields <- entrez_db_searchable("pmc")
pmc_fields[["AFFL"]]
entrez_search(db="pmc", term="Otago[AFFL]", retmax=0)
entrez_search(db="pmc", term="Auckland[AFFL]", retmax=0)

sra_fields <- entrez_db_searchable("sra")
as.data.frame(sra_fields)
} # }
```
