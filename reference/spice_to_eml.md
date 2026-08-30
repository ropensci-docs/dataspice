# Convert `dataspice` metadata to EML

Performs an (imperfect) conversion of `dataspice` metadata to EML. It's
very likely you will get validation errors and need to fix them
afterwards but `spice_to_eml` is a good way to a richer metadata schema
(EML) when you're already using `dataspice` but need a richer metadata
schema.

## Usage

``` r
spice_to_eml(spice = file.path("data", "metadata", "dataspice.json"))
```

## Arguments

- spice:

  (list) Your `dataspice` metadata. Uses `data/metadata/dataspice.json`
  by default.

## Value

(emld) The crosswalked `emld` object

## Examples

``` r
# Load an example dataspice JSON that comes installed with the package
spice <- system.file(
  "examples", "annual-escapement.json",
  package = "dataspice"
)

# And crosswalk it to EML
spice_to_eml(spice)
#> Warning: variableMeasured not crosswalked to EML because we don't have enough information. Use `crosswalk_variables` to create the start of an EML attributes table. See ?crosswalk_variables for help.
#> You might want to run EML::eml_validate on the result at this point and fix what validations errors are produced. You will commonly need to set `packageId`, `system`, and provide `attributeList` elements for each `dataTable`.
#> dataset:
#>   title: Compiled annual statewide Alaskan salmon escapement counts, 1921-2017
#>   creator:
#>   - individualName:
#>       givenName: Jeanette
#>       surName: Clark
#>     organizationName:
#>     - Organization
#>     electronicMailAddress: jclark@nceas.ucsb.edu
#>     userId: ~
#>   - individualName:
#>       givenName: Rich
#>       surName: Brenner
#>     organizationName:
#>     - Organization
#>     electronicMailAddress: richard.brenner.alaska.gov
#>     userId: ~
#>   abstract: The number of mature salmon migrating from the marine environment to freshwater
#>     streams is defined as escapement. Escapement data are the enumeration of these
#>     migrating fish as they pass upstream, and are a widely used index of spawning
#>     salmon abundance. These data are important for fisheries management, since most
#>     salmon harvest occurs near the mouths of rivers where salmon spawn during this
#>     migration. Escapement data are collected in a variety of ways. Stationary projects
#>     utilize observers stationed along freshwater corridors who count salmon as they
#>     pass upriver through weirs or past elevated towers. Sonar equipment placed in
#>     the river can also give a stationary escapement count. These counts usually represent
#>     a sample, and are expanded to represent a 24h period. Escapement data can also
#>     be collected using aerial surveys, where observers in an aircraft provide an index
#>     to estimate escapement. In general, escapement counts do not represent total abundance,
#>     but instead an index of abundance. Surveys are usually timed to coincide with
#>     peak spawning activity, generally in the summer, but in the case of Coho salmon
#>     in the fall as well. Some data about non-salmon species are also included. This
#>     dataset contains compiled annual data from multiple sources. The .Rmd merges all
#>     datasets, identifies and flags duplicate records, and performs quality assurance
#>     checks by filtering and graphing results.
#>   pubDate: ~
#>   coverage:
#>     temporalCoverage:
#>       rangeOfDates:
#>         beginDate:
#>           calendarDate: '1921-01-01'
#>           time: '08:00:00'
#>         endDate:
#>           calendarDate: '1921-01-01'
#>           time: '08:00:00'
#>     geographicCoverage:
#>       geographicDescription: Placeholder
#>       boundingCoordinates:
#>         westBoundingCoordinate: '-171'
#>         eastBoundingCoordinate: '-131'
#>         northBoundingCoordinate: '78'
#>         southBoundingCoordinate: '47'
#>   contact:
#>   - individualName:
#>       givenName: Jeanette
#>       surName: Clark
#>     organizationName:
#>     - Organization
#>     electronicMailAddress: jclark@nceas.ucsb.edu
#>     userId: ~
#>   - individualName:
#>       givenName: Rich
#>       surName: Brenner
#>     organizationName:
#>     - Organization
#>     electronicMailAddress: richard.brenner.alaska.gov
#>     userId: ~
#>   dataTable:
#>   - entityName: StockInfo.csv
#>     physical:
#>       objectName: StockInfo.csv
#>       dataFormat:
#>         externallyDefinedFormat:
#>           formatName: CSV
#>       distribution:
#>         online:
#>           url: http://example.com
#>   - entityName: BroodTables.csv
#>     physical:
#>       objectName: BroodTables.csv
#>       dataFormat:
#>         externallyDefinedFormat:
#>           formatName: CSV
#>       distribution:
#>         online:
#>           url: http://example.com
#>   - entityName: SourceInfo.csv
#>     physical:
#>       objectName: SourceInfo.csv
#>       dataFormat:
#>         externallyDefinedFormat:
#>           formatName: CSV
#>       distribution:
#>         online:
#>           url: http://example.com

# We can also create dataspice metadata from scratch and crosswalk it to EML
myspice <- list(
  name = "My example spice",
  creator = "Me",
  contact = "Me"
)
spice_to_eml(myspice)
#> Warning: Failed to crosswalk creator Me because it needs a type.
#> Warning: Failed to crosswalk creator Me because it needs a type.
#> dataset:
#>   title: My example spice
#>   creator:
#>   - []
#>   abstract: ~
#>   pubDate: ~
#>   coverage:
#>     temporalCoverage: []
#>     geographicCoverage: []
#>   contact:
#>   - []
#>   dataTable: []
```
