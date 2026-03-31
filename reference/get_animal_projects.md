# Get animal project data

Get data for animal projects, with options to filter results.

## Usage

``` r
get_animal_projects(connection, animal_project_code = NULL)
```

## Arguments

- connection:

  **\[deprecated\]** A connection to the ETN database. This argument is
  no longer used. You will be prompted for credentials instead.

- animal_project_code:

  Character (vector). One or more animal project codes.
  Case-insensitive.

## Value

A tibble with animal project data, sorted by `project_code`. See also
[field
definitions](https://inbo.github.io/etn/articles/etn_fields.html).

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()
# Get all animal projects
get_animal_projects()

# Get a specific animal project
get_animal_projects(animal_project_code = "2014_demer")
}
```
