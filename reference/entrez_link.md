# Get links to datasets related to records from an NCBI database

Discover records related to a set of unique identifiers from an NCBI
database. The object returned by this function depends on the value set
for the `cmd` argument. Printing the returned object lists the names ,
and provides a brief description, of the elements included in the
object.

## Usage

``` r
entrez_link(
  dbfrom,
  web_history = NULL,
  id = NULL,
  db = NULL,
  cmd = "neighbor",
  by_id = FALSE,
  config = NULL,
  ...
)
```

## Arguments

- dbfrom:

  character Name of database from which the Id(s) originate

- web_history:

  a web_history object

- id:

  vector with unique ID(s) for records in database `db`.

- db:

  character Name of the database to search for links (or use "all" to
  search all databases available for `db`. `entrez_db_links` allows you
  to discover databases that might have linked information (see
  examples).

- cmd:

  link function to use. Allowed values include

  - neighbor (default). Returns a set of IDs in `db` linked to the input
    IDs in `dbfrom`.

  - neighbor_score. As \`neighbor”, but additionally returns similarity
    scores.

  - neighbor_history. As \`neighbor', but returns web history objects.

  - acheck. Returns a list of linked databases available from NCBI for a
    set of IDs.

  - ncheck. Checks for the existence of links within a single database.

  - lcheck. Checks for external (i.e. outside NCBI) links.

  - llinks. Returns a list of external links for each ID, excluding
    links provided by libraries.

  - llinkslib. As 'llinks' but additionally includes links provided by
    libraries.

  - prlinks. As 'llinks' but returns only the primary external link for
    each ID.

- by_id:

  logical If FALSE (default) return a single `elink` objects containing
  links for all of the provided `id`s. Alternatively, if TRUE return a
  list of `elink` objects, one for each ID in `id`.

- config:

  vector configuration options passed to httr::GET

- ...:

  character Additional terms to add to the request, see NCBI
  documentation linked to in references for a complete list

## Value

An elink object containing the data defined by the `cmd` argument (if
by_id=FALSE) or a list of such object (if by_id=TRUE).

file XMLInternalDocument xml file resulting from search, parsed with
[`xmlTreeParse`](https://rdrr.io/pkg/XML/man/xmlTreeParse.html)

## References

<https://www.ncbi.nlm.nih.gov/books/NBK25499/#_chapter4_ELink_>

## See also

[`config`](https://httr.r-lib.org/reference/config.html) for available
configs

`entrez_db_links`

## Examples

``` r
if (FALSE) { # \dontrun{
 pubmed_search <- entrez_search(db = "pubmed", term ="10.1016/j.ympev.2010.07.013[doi]")
 linked_dbs <- entrez_db_links("pubmed")
 linked_dbs
 nucleotide_data <- entrez_link(dbfrom = "pubmed", id = pubmed_search$ids, db ="nuccore")
 #Sources for the full text of the paper 
 res <- entrez_link(dbfrom="pubmed", db="", cmd="llinks", id=pubmed_search$ids)
 linkout_urls(res)
} # }
```
