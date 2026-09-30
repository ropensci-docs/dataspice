# Prepare attributes

Extract `variableNames` from data file(s) and add them to
`attributes.csv`. The helper
[`validate_file_paths`](https://docs.ropensci.org/dataspice/reference/validate_file_paths.md)
can be used to create vectors of valid file paths that can be checked
and then passed as `data_path` argument to `prep_attributes`.

## Usage

``` r
prep_attributes(
  data_path = "data",
  attributes_path = file.path("data", "metadata", "attributes.csv"),
  ...
)
```

## Arguments

- data_path:

  character vector of either:

  1.  path(s) to the data file(s).

  2.  single path to directory containing data file(s). Currently only
      tabular `.csv` and `.tsv` files are supported. Alternatively
      attributes returned using
      [`names()`](https://rdrr.io/r/base/names.html) can be extracted
      from r object, stored as `.rds` files.

- attributes_path:

  path to the
  ``` attributes.csv`` file. Defaults to  ```data/metadata/attributes.csv\`.

- ...:

  parameters passed to
  [`list.files()`](https://rdrr.io/r/base/list.files.html). For example,
  use `recursive = TRUE` to list files in a folder recursively or use
  `pattern` to filter files for patterns.

## Value

`prep_attributes()` updates the `attributes.csv` and writes to
`attributes_path`.

## Examples

``` r
if (FALSE) { # \dontrun{
create_spice()
# extract attributes from all `csv`, `tsv`, `rds` files in the data folder
# (non recursive)
prep_attributes()
# recursive
prep_attributes(recursive = TRUE)
# extract attributes from a single file using file path
data_path <- system.file("example-dataset","BroodTables.csv",
                         package = "dataspice")
prep_attributes(data_path)
# extract attributes from a single file by file path pattern matching
data_path <- system.file("example-dataset", package = "dataspice")
prep_attributes(data_path, pattern = "StockInfo")
# extract from a folder using folder path
data_path <- system.file("example-dataset", package = "dataspice")
prep_attributes(data_path)
} # }
```
