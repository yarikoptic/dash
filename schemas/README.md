# Schema for inputs to the dashboard

## `bagel_schema.json`
This file describes the recognized columns in tabular inputs to the dashboard (`bagel.csv`).

In the schema, columns are organized into two categories:  
`GLOBAL_COLUMNS`: Includes columns describing metadata that should have the same meaning regardless of pipeline, and does not depend on pipeline outputs.  
`PIPELINE_STATUS_COLUMNS`: Includes columns conveying information about pipeline completion that depends on pipeline-specific outputs and may vary depending on the pipeline tracker used.

A specific named column can have the following attributes:
- `Description`
  - Describes the column contents, along with the meaning of different acceptable values for categorical columns.
- `dtype`
  - The expected type for values in the column.
- `IsRequired`
  - Whether or not the column is required to be present in `bagel.csv`. If `true`, the dashboard will throw an error if the column is missing.
- `Range`
  - Acceptable values for data in the column. Only present for categorical columns.
- `MissingValue`
  - The value expected to denote that data is not available for the column. Only present for non-categorical columns.
- `IsPrefixedColumn`
  - Whether or not this column will be recognized by a prefix in the column name. If `true`, columns with this prefix are expected to have unique user-defined informative suffixes in line with the  `Description`. More than one column can have the same prefix.
