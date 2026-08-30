# Write spice

Write out your metadata as a dataspice JSON-LD document

## Usage

``` r
write_spice(path = file.path("data", "metadata"), ...)
```

## Arguments

- path:

  location of metadata files

- ...:

  additional arguments to
  [`jsonlite::toJSON()`](https://jeroen.r-universe.dev/jsonlite/reference/fromJSON.html)

## Value

A JSON-LD file at the path specified

## Examples

``` r
if (FALSE) { # \dontrun{
# First create your metadata templates
create_spice()

# Then fill in the template files however you like

# Then write out your dataspice file
write_spice()
} # }
```
