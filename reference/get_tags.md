# Get tag data

Get data for tags, with options to filter results. Note that there can
be multiple records (`acoustic_tag_id`) per tag device
(`tag_serial_number`).

## Usage

``` r
get_tags(
  connection,
  tag_type = NULL,
  tag_subtype = NULL,
  tag_serial_number = NULL,
  acoustic_tag_id = NULL
)
```

## Arguments

- connection:

  **\[deprecated\]** A connection to the ETN database. This argument is
  no longer used. You will be prompted for credentials instead.

- tag_type:

  Character (vector). `acoustic` or `archival`. Some tags are both, find
  those with `acoustic-archival`.

- tag_subtype:

  Character (vector). `animal`, `built-in`, `range` or `sentinel`.

- tag_serial_number:

  Character (vector). One or more tag serial numbers.

- acoustic_tag_id:

  Character (vector). One or more acoustic tag identifiers, i.e.
  identifiers found in
  [`get_acoustic_detections()`](https://inbo.github.io/etn/reference/get_acoustic_detections.md).

## Value

A tibble with tags data, sorted by `tag_serial_number`. See also [field
definitions](https://inbo.github.io/etn/articles/etn_fields.html).
Values for `owner_organization` and `owner_pi` will only be visible if
you are member of the group.

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()
# Get all tags
get_tags()

# Get archival tags, including acoustic-archival
get_tags(tag_type = c("archival", "acoustic-archival"))

# Get tags of specific subtype
get_tags(tag_subtype = c("built-in", "range"))

# Get specific tags (note that these can return multiple records)
get_tags(tag_serial_number = "1187450")
get_tags(acoustic_tag_id = "A69-1601-16130")
get_tags(acoustic_tag_id = c("A69-1601-16129", "A69-1601-16130"))
}
```
