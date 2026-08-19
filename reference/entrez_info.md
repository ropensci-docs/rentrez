# Get information about EUtils databases

Gather information about EUtils generally, or a given Eutils database.
Note: The most common uses-cases for the einfo util are finding the list
of search fields available for a given database or the other NCBI
databases to which records in a given database might be linked. Both
these use cases are implemented in higher-level functions that return
just this information (`entrez_db_searchable` and `entrez_db_links`
respectively). Consequently most users will not have a reason to use
this function (though it is exported by `rentrez` for the sake of
completeness.

## Usage

``` r
entrez_info(db = NULL, config = NULL)
```

## Arguments

- db:

  character database about which to retrieve information (optional)

- config:

  config vector passed on to
  [`httr::GET`](https://httr.r-lib.org/reference/GET.html)

## Value

XMLInternalDocument with information describing either all the databases
available in Eutils (if db is not set) or one particular database (set
by 'db')

## See also

[`config`](https://httr.r-lib.org/reference/config.html) for available
httr configurations

Other einfo:
[`entrez_db_links()`](https://docs.ropensci.org/rentrez/reference/entrez_db_links.md),
[`entrez_db_searchable()`](https://docs.ropensci.org/rentrez/reference/entrez_db_searchable.md),
[`entrez_db_summary()`](https://docs.ropensci.org/rentrez/reference/entrez_db_summary.md),
[`entrez_dbs()`](https://docs.ropensci.org/rentrez/reference/entrez_dbs.md)

## Examples

``` r
if (FALSE) { # \dontrun{
all_the_data <- entrez_info()
XML::xpathSApply(all_the_data, "//DbName", xmlValue)
entrez_dbs()
} # }
```
