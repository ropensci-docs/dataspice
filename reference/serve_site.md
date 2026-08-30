# Serve site

Serve site

## Usage

``` r
serve_site(path = "docs")
```

## Arguments

- path:

  (character) Optional. Directory to serve. Defaults to `docs`.

## Value

Nothing.

## Examples

``` r
if (FALSE) { # \dontrun{
# Build your site
json <- write_json(biblio, access, attributes, creators)
build_site(json)

# Serve it
serve_site()
} # }
```
