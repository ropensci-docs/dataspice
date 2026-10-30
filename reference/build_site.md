# Build a dataspice site

Build a dataspice site

## Usage

``` r
build_site(
  path = file.path("data", "metadata", "dataspice.json"),
  template_path = system.file("template.html5", package = "dataspice"),
  out_path = file.path("docs", "index.html")
)
```

## Arguments

- path:

  (character) Path to a JSON+LD file with dataspice metadata

- template_path:

  (character) Optional. Path to a template for
  [`whisker.render`](https://rdrr.io/pkg/whisker/man/whisker.render.html)

- out_path:

  (character) Optional. Path to write the site's `index.html` to.
  Defaults to `docs/index.html`.

## Value

Nothing. Creates/overwrites `docs/index.html`

## Examples

``` r
if (FALSE) { # \dontrun{
# Create JSON+LD from a set of metadata templates
json <- write_json(biblio, access, attributes, creators)
build_site(json)
} # }
```
