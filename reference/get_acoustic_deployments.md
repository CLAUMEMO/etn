# Get acoustic deployment data

Get data for deployments of acoustic receivers, with options to filter
results.

## Usage

``` r
get_acoustic_deployments(
  connection,
  deployment_id = NULL,
  receiver_id = NULL,
  acoustic_project_code = NULL,
  station_name = NULL,
  open_only = FALSE
)
```

## Arguments

- connection:

  **\[deprecated\]** A connection to the ETN database. This argument is
  no longer used. You will be prompted for credentials instead.

- deployment_id:

  Integer (vector). One or more deployment identifiers.

- receiver_id:

  Character (vector). One or more receiver identifiers.

- acoustic_project_code:

  Character (vector). One or more acoustic project codes.
  Case-insensitive.

- station_name:

  Character (vector). One or more deployment station names.

- open_only:

  Logical. Restrict deployments to those that are currently open (i.e.
  no end date defined). Defaults to `FALSE`.

## Value

A tibble with acoustic deployment data, sorted by
`acoustic_project_code`, `station_name` and `deploy_date_time`. See also
[field
definitions](https://inbo.github.io/etn/articles/etn_fields.html).

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()
# Get all acoustic deployments
get_acoustic_deployments()

# Get specific acoustic deployment
get_acoustic_deployments(deployment_id = 1437)

# Get acoustic deployments for a specific receiver
get_acoustic_deployments(receiver_id = "VR2W-124070")

# Get open acoustic deployments for a specific receiver
get_acoustic_deployments(receiver_id = "VR2W-124070", open_only = TRUE)

# Get acoustic deployments for a specific acoustic project
get_acoustic_deployments(acoustic_project_code = "demer")

# Get acoustic deployments for two specific stations
get_acoustic_deployments(station_name = c("de-9", "de-10"))
}
```
