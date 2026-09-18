# Summarize an XML record from pubmed.

Note: this function assumes all records are of the type "PubmedArticle"
and will return an empty record for any other type (including books).

## Usage

``` r
parse_pubmed_xml(record)
```

## Arguments

- record:

  Either and XMLInternalDocument or character the record to be parsed (
  expected to come from
  [`entrez_fetch`](https://docs.ropensci.org/rentrez/reference/entrez_fetch.md))

## Value

Either a single pubmed_record object, or a list of several

## Examples

``` r
# \donttest{
hox_paper <- entrez_search(db="pubmed", term="10.1038/nature08789[doi]")
hox_rel <- entrez_link(db="pubmed", dbfrom="pubmed", id=hox_paper$ids)
recs <- entrez_fetch(db="pubmed", 
                       id=hox_rel$links$pubmed_pubmed[1:3], 
                       rettype="xml")
parse_pubmed_xml(recs)
#> List of 3 pubmed records
#>  Di-Poï, Nicolas et al. (2010).  Nature. 464:99-103 
#>  Feiner, Nathalie. & Wood, Natalie J. (2019).  Evolution & development. 21:218-228 
#>  Woltering, Joost M et al. (2009).  Developmental biology. 332:82-9 
# }
```
