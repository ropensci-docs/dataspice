# Validate file paths

Helper function to return a set of file paths for use in other functions

## Usage

``` r
validate_file_paths(data_path = "data", ...)
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

- ...:

  parameters passed to
  [`list.files()`](https://rdrr.io/r/base/list.files.html). For example,
  use `recursive = TRUE` to list files in a folder recursively or use
  `pattern` to filter files for patterns.

## Value

One or more data file paths

## Examples

``` r
if (FALSE) { # \dontrun{
# Assuming some data files in "./data"
my_files <- validate_file_paths()

# If your data files are in `another_folder`
my_files <- validate_file_paths("another_folder")
} # }
```
