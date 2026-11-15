# List available links for records from a given NCBI database

For a given database, fetch a list of other databases that contain
cross-referenced records. The names of these records can be used as the
`db` argument in
[`entrez_link`](https://docs.ropensci.org/rentrez/reference/entrez_link.md)

## Usage

``` r
entrez_db_links(db, config = NULL)
```

## Arguments

- db:

  character, name of database to search

- config:

  config vector passed to
  [`httr::GET`](https://httr.r-lib.org/reference/GET.html)

## Value

An eInfoLink object (sub-classed from list) summarizing
linked-databases. Can be coerced to a data-frame with `as.data.frame`.
Printing the object the name of each element (which is the correct name
for `entrez_link`, and can be used to get (a little) more information
about each linked database (see example below).

## See also

[`entrez_link`](https://docs.ropensci.org/rentrez/reference/entrez_link.md)

Other einfo:
[`entrez_db_searchable()`](https://docs.ropensci.org/rentrez/reference/entrez_db_searchable.md),
[`entrez_db_summary()`](https://docs.ropensci.org/rentrez/reference/entrez_db_summary.md),
[`entrez_dbs()`](https://docs.ropensci.org/rentrez/reference/entrez_dbs.md),
[`entrez_info()`](https://docs.ropensci.org/rentrez/reference/entrez_info.md)

## Examples

``` r
if (FALSE) { # \dontrun{
taxid <- entrez_search(db="taxonomy", term="Osmeriformes")$ids
tax_links <- entrez_db_links("taxonomy")
tax_links
entrez_link(dbfrom="taxonomy", db="pmc", id=taxid)

sra_links <- entrez_db_links("sra")
as.data.frame(sra_links)
} # }
```
