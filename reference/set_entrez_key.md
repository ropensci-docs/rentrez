# Set the ENTREZ_KEY variable to be used by all rentrez functions

The NCBI allows users to access more records (10 per second) if they
register for and use an API key. This function allows users to set this
key for all calls to rentrez functions during a particular R session.
See the vignette section "Using API keys" for a detailed description.

## Usage

``` r
set_entrez_key(key)
```

## Arguments

- key:

  character. Value to set ENTREZ_KEY to (i.e. your API key).

## Value

A logical of length one, TRUE is the value was set FALSE if not. value
is returned inside invisible(), i.e. it is not printed to screen when
the function is called.
