# Retrieve summary information about an NCBI database

Retrieve summary information about an NCBI database

## Usage

``` r
entrez_db_summary(db, config = NULL)
```

## Arguments

- db:

  character, name of database to summaries

- config:

  config vector passed to
  [`httr::GET`](https://httr.r-lib.org/reference/GET.html)

## Value

Character vector with the following data

DbName Name of database

Description Brief description of the database

Count Number of records contained in the database

MenuName Name in web-interface to EUtils

DbBuild Unique ID for current build of database

LastUpdate Date of most recent update to database

## See also

Other einfo:
[`entrez_db_links()`](https://docs.ropensci.org/rentrez/reference/entrez_db_links.md),
[`entrez_db_searchable()`](https://docs.ropensci.org/rentrez/reference/entrez_db_searchable.md),
[`entrez_dbs()`](https://docs.ropensci.org/rentrez/reference/entrez_dbs.md),
[`entrez_info()`](https://docs.ropensci.org/rentrez/reference/entrez_info.md)

## Examples

``` r
if (FALSE) { # \dontrun{
entrez_db_summary("pubmed")
} # }
```
