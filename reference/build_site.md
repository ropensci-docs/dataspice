# Build a dataspice site

Build a dataspice site

## Usage

``` r
build_site(
  path = file.path("data", "metadata", "dataspice.json"),
  template_path = system.file("template.html5", package = "dataspice"),
  out_path = file.path("docs", "index.html"),
  static_map = FALSE,
  static_map_method = "default"
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

- static_map:

  (logical) Use a self-contained static map image instead of the default
  Leaflet map. Defaults to `FALSE`. The image includes latitude and
  longitude graticules and an Equal Earth locator inset. This argument
  is experimental and may change.

- static_map_method:

  (character) Projection for the static map. Defaults to the built-in
  extent-aware method `"default"`. Other choices are `"crsuggest"`,
  `"equalearth"`, or a custom PROJ string beginning with `"+proj="`.
  This argument is experimental and may change.

## Value

Nothing. Creates/overwrites `out_path`.

## Examples

``` r
if (FALSE) { # \dontrun{
# Create JSON+LD from a set of metadata templates
json <- write_json(biblio, access, attributes, creators)
build_site(json)
} # }
```
