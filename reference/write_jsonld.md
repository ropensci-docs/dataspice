# Write a list out as object to JSON-LD

Write a list out as object to JSON-LD

## Usage

``` r
write_jsonld(
  x,
  path,
  context = "http://schema.org",
  pretty = TRUE,
  auto_unbox = TRUE,
  ...
)
```

## Arguments

- x:

  an object to be serialized to JSON

- path:

  file on disk

- context:

  JSON-LD context; "http://schema.org"

- pretty:

  adds indentation whitespace to JSON output. Can be TRUE/FALSE or a
  number specifying the number of spaces to indent. See
  [`prettify`](https://jeroen.r-universe.dev/jsonlite/reference/prettify.html)

- auto_unbox:

  automatically
  [`unbox`](https://jeroen.r-universe.dev/jsonlite/reference/unbox.html)
  all atomic vectors of length 1. It is usually safer to avoid this and
  instead use the
  [`unbox`](https://jeroen.r-universe.dev/jsonlite/reference/unbox.html)
  function to unbox individual elements. An exception is that objects of
  class `AsIs` (i.e. wrapped in
  [`I()`](https://rdrr.io/r/base/AsIs.html)) are not automatically
  unboxed. This is a way to mark single values as length-1 arrays.

- ...:

  additional conversion arguments, see also
  [toJSON](https://jeroen.r-universe.dev/jsonlite/reference/fromJSON.html)
  or
  [fromJSON](https://jeroen.r-universe.dev/jsonlite/reference/fromJSON.html)
