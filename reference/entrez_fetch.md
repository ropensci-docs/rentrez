# Download data from NCBI databases

Pass unique identifiers to an NCBI database and receive data files in a
variety of formats. A set of unique identifiers mustbe specified with
either the `db` argument (which directly specifies the IDs as a numeric
or character vector) or a `web_history` object as returned by
[`entrez_link`](https://docs.ropensci.org/rentrez/reference/entrez_link.md),
[`entrez_search`](https://docs.ropensci.org/rentrez/reference/entrez_search.md)
or
[`entrez_post`](https://docs.ropensci.org/rentrez/reference/entrez_post.md).

## Usage

``` r
entrez_fetch(
  db,
  id = NULL,
  web_history = NULL,
  rettype,
  retmode = "",
  parsed = FALSE,
  config = NULL,
  ...
)
```

## Arguments

- db:

  character, name of the database to use

- id:

  vector (numeric or character), unique ID(s) for records in database
  `db`. In the case of sequence databases these IDs can take form of an
  NCBI accession followed by a version number (eg AF123456.1 or
  AF123456.2).

- web_history, :

  a web_history object

- rettype:

  character, format in which to get data (eg, fasta, xml...)

- retmode:

  character, mode in which to receive data, defaults to an empty string
  (corresponding to the default mode for rettype).

- parsed:

  boolean should entrez_fetch attempt to parse the resulting file. Only
  works with xml records (including those with rettypes other than
  "xml") at present

- config:

  vector, httr configuration options passed to httr::GET

- ...:

  character, additional terms to add to the request, see NCBI
  documentation linked to in references for a complete list

## Value

character string containing the file created

XMLInternalDocument a parsed XML document if parsed=TRUE and rettype is
a flavour of XML.

## Details

The format for returned records is set by that arguments `rettype` (for
a particular format) and `retmode` for a general format (JSON, XML text
etc). See [Table
1](https://www.ncbi.nlm.nih.gov/books/NBK25499/table/chapter4.T._valid_values_of__retmode_and/)
in the linked reference for the set of formats available for each
database. In particular, note that sequence databases (nuccore, protein
and their relatives) use specific format names (eg "native", "ipg") for
different flavours of xml.

For the most part, this function returns a character vector containing
the fetched records. For XML records (including 'native', 'ipg', 'gbc'
sequence records), setting `parsed` to `TRUE` will return an
`XMLInternalDocument`,

## References

<https://www.ncbi.nlm.nih.gov/books/NBK25499/#_chapter4_EFetch_>

## See also

[`config`](https://httr.r-lib.org/reference/config.html) for available
'`httr`\` configs

## Examples

``` r
if (FALSE) { # \dontrun{
katipo <- "Latrodectus katipo[Organism]"
katipo_search <- entrez_search(db="nuccore", term=katipo)
kaitpo_seqs <- entrez_fetch(db="nuccore", id=katipo_search$ids, rettype="fasta")
#xml
kaitpo_seqs <- entrez_fetch(db="nuccore", id=katipo_search$ids, rettype="native")
} # }
```
