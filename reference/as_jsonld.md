# Convert a list object to JSON-LD

Convert a list object to JSON-LD

## Usage

``` r
as_jsonld(
  x,
  context = "http://schema.org",
  pretty = TRUE,
  auto_unbox = TRUE,
  ...
)
```

## Arguments

- x:

  the object to be encoded.

- context:

  JSON-LD context; "http://schema.org".

- pretty:

  Whether or not to prettify output. See
  [`toJSON`](https://jeroen.r-universe.dev/jsonlite/reference/fromJSON.html).

- auto_unbox:

  Whether or not to automatically unbox output. See
  [`toJSON`](https://jeroen.r-universe.dev/jsonlite/reference/fromJSON.html).

- ...:

  Other arguments to be passed to
  [`toJSON`](https://jeroen.r-universe.dev/jsonlite/reference/fromJSON.html).
