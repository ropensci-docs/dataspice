# Shiny apps for editing dataspice metadata tables

Launch Shiny app for editing individual `dataspice` metadata tables. Use
`edit_*()` where `*` is one of the four `dataspice` metadata tables
**`attributes`, `biblio`, `access` or `creators`**.

## Usage

``` r
edit_biblio(metadata_dir = file.path("data", "metadata"))
```

## Arguments

- metadata_dir:

  the directory containing the `dataspice` metadata `.csv` files.
  Defaults to `data/metadata/` directory in **current project root**.

## Examples
