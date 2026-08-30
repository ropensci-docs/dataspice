# Create dataspice metadata tables from EML

Create dataspice metadata tables from EML

## Usage

``` r
eml_to_spice(eml, path = NULL)
```

## Arguments

- eml:

  (emld) An EML object

- path:

  (character) Folder path for saving the tables to disk

## Value

A list with names `attributes`, `access`, `biblio`, and `creators`.
Optionally, if `path` is specified, saves the four tables as `CSV`
files.

## Examples

``` r
if (FALSE) { # \dontrun{
# First, load up an example EML record
library(EML)

eml_path <- system.file(
 file.path("example-dataset", "broodTable_metadata.xml"),
 package = "dataspice")
eml <- read_eml(eml_path)


# Generate the four dataspice tables
my_spice <- eml_to_spice(eml)

# Or save them as a file
# Generate the four dataspice tables
eml_to_spice(eml, ".")
} # }
```
