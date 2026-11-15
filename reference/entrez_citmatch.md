# Fetch pubmed ids matching specially formatted citation strings

Fetch pubmed ids matching specially formatted citation strings

## Usage

``` r
entrez_citmatch(bdata, db = "pubmed", retmode = "xml", config = NULL)
```

## Arguments

- bdata:

  character, containing citation data. Each citation must be represented
  in a pipe-delimited format
  journal_title\|year\|volume\|first_page\|author_name\|your_key\| The
  final field "your_key" is arbitrary, and can used as you see fit.
  Fields can be left empty, but be sure to keep 6 pipes.

- db:

  character, the database to search. Defaults to pubmed, the only
  database currently available

- retmode:

  character, file format to retrieve. Defaults to xml, as per the API
  documentation, though note the API only returns plain text

- config:

  vector configuration options passed to httr::GET

## Value

A character vector containing PMIDs

## See also

[`config`](https://httr.r-lib.org/reference/config.html) for available
configs

## Examples

``` r
if (FALSE) { # \dontrun{
ex_cites <- c("proc natl acad sci u s a|1991|88|3248|mann bj|test1|",
              "science|1987|235|182|palmenberg ac|test2|")
entrez_citmatch(ex_cites)
} # }
```
