# Post IDs to Eutils for later use

Post IDs to Eutils for later use

## Usage

``` r
entrez_post(db, id = NULL, web_history = NULL, config = NULL, ...)
```

## Arguments

- db:

  character Name of the database from which the IDs were taken

- id:

  vector with unique ID(s) for records in database `db`.

- web_history:

  A web_history object. Can be used to add to additional identifiers to
  an existing web environment on the NCBI

- config:

  vector of configuration options passed to httr::GET

- ...:

  character Additional terms to add to the request, see NCBI
  documentation linked to in references for a complete list

## References

<https://www.ncbi.nlm.nih.gov/books/NBK25499/#_chapter4_EPost_>

## See also

[`config`](https://httr.r-lib.org/reference/config.html) for available
httr configurations

## Examples

``` r
if (FALSE) { # \dontrun{  
so_many_snails <- entrez_search(db="nuccore", 
                      "Gastropoda[Organism] AND COI[Gene]", retmax=200)
upload <- entrez_post(db="nuccore", id=so_many_snails$ids)
first <- entrez_fetch(db="nuccore", rettype="fasta", web_history=upload,
                      retmax=10)
second <- entrez_fetch(db="nuccore", file_format="fasta", web_history=upload,
                       retstart=10, retmax=10)
} # }
```
