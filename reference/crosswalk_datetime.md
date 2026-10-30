# Convert a date(time) of unknown format into EML

A quick and dirty crosswalk of an unknown date(time) input to EML that
really only works for ISO8601 input. All other formats will fail and be
returned as-is as a `calendarDate`. From there the user will need to do
a conversion themselves.

## Usage

``` r
crosswalk_datetime(input)
```

## Arguments

- input:

  (character) Some unknown date(time) input

## Value

(list) A `list` with members `calendarDate` and `time`. `time` will be
`NULL` if parsing fails or if the time string inside `input` isn't
ISO8601
