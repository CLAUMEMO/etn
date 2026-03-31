# Get acoustic receiver data

Get data for acoustic receivers, with options to filter results.

## Usage

``` r
get_acoustic_receivers(connection, receiver_id = NULL, status = NULL)
```

## Arguments

- connection:

  **\[deprecated\]** A connection to the ETN database. This argument is
  no longer used. You will be prompted for credentials instead.

- receiver_id:

  Character (vector). One or more receiver identifiers.

- status:

  Character. One or more statuses, e.g. `available` or `broken`.

## Value

A tibble with acoustic receiver data, sorted by `receiver_id`. See also
[field
definitions](https://inbo.github.io/etn/articles/etn_fields.html).
Values for `owner_organization` will only be visible if you are member
of the group.

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()
# Get all acoustic receivers
get_acoustic_receivers()

# Get lost and broken acoustic receivers
get_acoustic_receivers(status = c("lost", "broken"))

# Get a specific acoustic receiver
get_acoustic_receivers(receiver_id = "VR2W-124070")
}
```
