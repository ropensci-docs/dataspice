# Prepare access

Extract `fileNames` from data file(s) and add them to `access.csv`. The
helper
[`validate_file_paths`](https://docs.ropensci.org/dataspice/reference/validate_file_paths.md)
can be used to create vectors of valid file paths that can be checked
and then passed as `data_path` argument to `prep_access`.

## Usage

``` r
prep_access(
  data_path = "data",
  access_path = file.path("data", "metadata", "access.csv"),
  ...
)
```

## Arguments

- data_path:

  character vector of either:

  1.  path(s) to the data file(s).

  2.  single path to directory containing data file(s). Currently only
      tabular `.csv` and `.tsv` or `.rds` files are supported.

- access_path:

  path to the `access.csv` file. Defaults to `data/metadata/access.csv`.

- ...:

  parameters passed to
  [`list.files()`](https://rdrr.io/r/base/list.files.html). For example,
  use `recursive = TRUE` to list files in a folder recursively or use
  `pattern` to filter files for patterns.

## Value

Updates `access.csv` and writes to `access_path`.

## Examples

``` r
if (FALSE) { # \dontrun{
# First create the metadata tempaltes
create_spice()

# Then begin filling them in from your data files
prep_access()
} # }
```
