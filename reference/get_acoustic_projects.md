# Get acoustic project data

Get data for acoustic projects, with options to filter results.

## Usage

``` r
get_acoustic_projects(connection, acoustic_project_code = NULL)
```

## Arguments

- connection:

  **\[deprecated\]** A connection to the ETN database. This argument is
  no longer used. You will be prompted for credentials instead.

- acoustic_project_code:

  Character (vector). One or more acoustic project codes.
  Case-insensitive.

## Value

A tibble with acoustic project data, sorted by `project_code`. See also
[field
definitions](https://inbo.github.io/etn/articles/etn_fields.html).

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()
# Get all acoustic projects
get_acoustic_projects()

# Get a specific acoustic project
get_acoustic_projects(acoustic_project_code = "demer")
}
```
