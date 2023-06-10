# CatalogDiff

Describes the difference between two Airbyte catalogs.


## Fields

| Field                                                       | Type                                                        | Required                                                    | Description                                                 |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| `Transforms`                                                | [][StreamTransform](../../models/shared/streamtransform.md) | :heavy_check_mark:                                          | list of stream transformations. order does not matter.      |