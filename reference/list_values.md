# List all unique values from a data.frame column

Get a vector with all unique values found in a given column of a
data.frame. Concatenated values (`A,B`) in the column can be returned as
single values (`A` and `B`).

## Usage

``` r
list_values(.data, column, split = ",")
```

## Arguments

- .data:

  Data frame. Data.frame to select column from.

- column:

  Character or integer. Quoted or unqoted column name or column
  position.

- split:

  Character (vector). Character or regular expression(s) passed to
  [`strsplit()`](https://rdrr.io/r/base/strsplit.html) to split column
  values before returning unique values. Defaults to `,`.

## Value

A vector of the same type as the given column.

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()

# List unique scientific_name from a dataframe containing animal information
df <- get_animals(animal_project_code = "2014_demer")
list_values(df, "scientific_name")

# Or using pipe and unquoted column name
df |> list_values(scientific_name)

# Or using column position
df |> list_values(8)

# tag_serial_number can contain comma-separated values
df <- get_animals(animal_id = 5841)
df$tag_serial_number

# list_values() will split those and return unique values
list_values(df, tag_serial_number)

# Another expression can be defined to split values (here ".")
list_values(df, tag_serial_number, split = "\\.")
}
```
