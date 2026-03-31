# Get acoustic detections data

Get data for acoustic detections, with options to filter results. Use
`limit` to limit the number of returned records.

## Usage

``` r
get_acoustic_detections(
  connection,
  start_date = NULL,
  end_date = NULL,
  tag_serial_number = NULL,
  acoustic_tag_id = NULL,
  animal_project_code = NULL,
  scientific_name = NULL,
  acoustic_project_code = NULL,
  receiver_id = NULL,
  station_name = NULL,
  limit = FALSE,
  progress = TRUE
)
```

## Arguments

- connection:

  **\[deprecated\]** A connection to the ETN database. This argument is
  no longer used. You will be prompted for credentials instead.

- start_date:

  Character. Start date (inclusive) in ISO 8601 format ( `yyyy-mm-dd`,
  `yyyy-mm` or `yyyy`).

- end_date:

  Character. End date (exclusive) in ISO 8601 format ( `yyyy-mm-dd`,
  `yyyy-mm` or `yyyy`).

- tag_serial_number:

  Character (vector). One or more acoustic tag serial numbers.

- acoustic_tag_id:

  Character (vector). One or more acoustic tag ids.

- animal_project_code:

  Character (vector). One or more animal project codes.
  Case-insensitive.

- scientific_name:

  Character (vector). One or more scientific names.

- acoustic_project_code:

  Character (vector). One or more acoustic project codes.
  Case-insensitive.

- receiver_id:

  Character (vector). One or more receiver identifiers.

- station_name:

  Character (vector). One or more deployment station names.

- limit:

  Logical. Limit the number of returned records to 100 (useful for
  testing purposes). Defaults to `FALSE`.

- progress:

  Logical. Show a progress bar while fetching data. Defaults to `TRUE`.

## Value

A tibble with acoustic detections data, sorted by `acoustic_tag_id` and
`date_time`. See also [field
definitions](https://inbo.github.io/etn/articles/etn_fields.html).

## Examples

``` r
if (FALSE) { # etn:::credentials_are_set()
# Get limited sample of acoustic detections
get_acoustic_detections(limit = TRUE)

# Get all acoustic detections from a specific animal project
get_acoustic_detections(animal_project_code = "2014_demer")

# Get 2015 acoustic detections from that animal project
get_acoustic_detections(
  animal_project_code = "2014_demer",
  start_date = "2015",
  end_date = "2016",
)

# Get April 2015 acoustic detections from that animal project
get_acoustic_detections(
  animal_project_code = "2014_demer",
  start_date = "2015-04",
  end_date = "2015-05",
)

# Get April 24, 2015 acoustic detections from that animal project
get_acoustic_detections(
  animal_project_code = "2014_demer",
  start_date = "2015-04-24",
  end_date = "2015-04-25",
)

# Get acoustic detections for a specific tag at two specific stations
get_acoustic_detections(
  acoustic_tag_id = "A69-1601-16130",
  station_name = c("de-9", "de-10")
)

# Get acoustic detections for a specific species, receiver and acoustic project
get_acoustic_detections(
  scientific_name = "Rutilus rutilus",
  receiver_id = "VR2W-124070",
  acoustic_project_code = "demer"
)
}
```
