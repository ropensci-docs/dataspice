# Crosswalk `dataspice` variables to EML

See
[`set_attributes`](https://docs.ropensci.org/EML/reference/set_attributes.html)
for more information on what must be filled out after this is run in
order to get a valid EML `attributeList`.

## Usage

``` r
crosswalk_variables(spice)
```

## Arguments

- spice:

  (list) Your `dataspice` metadata

## Value

(data.frame) A partial EML attributes table

## Examples

``` r
if (FALSE) { # \dontrun{
# Load an example dataspice JSON that comes installed with the package
spice <- system.file(
  "examples", "annual-escapement.json",
  package = "dataspice")

# Convert it to EML (notice the warning)
eml_doc <- suppressWarnings({spice_to_eml(spice)})
attributes <- crosswalk_variables(spice)

# Now fill in the attributes data.frame. See `EML::set_attributes`.

# And last, set the attributes on our EML document
eml_doc$dataset$dataTable[[1]]$attributeList <-
  EML::set_attributes(attributes)
} # }
```
