# SynchronousJobRead


## Fields

| Field                                                 | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ConfigID`                                            | **string*                                             | :heavy_minus_sign:                                    | only present if a config id was provided.             |
| `ConfigType`                                          | [JobConfigType](../../models/shared/jobconfigtype.md) | :heavy_check_mark:                                    | N/A                                                   |
| `ConnectorConfigurationUpdated`                       | **bool*                                               | :heavy_minus_sign:                                    | N/A                                                   |
| `CreatedAt`                                           | *int64*                                               | :heavy_check_mark:                                    | N/A                                                   |
| `EndedAt`                                             | *int64*                                               | :heavy_check_mark:                                    | N/A                                                   |
| `ID`                                                  | *string*                                              | :heavy_check_mark:                                    | N/A                                                   |
| `Logs`                                                | [*LogRead](../../models/shared/logread.md)            | :heavy_minus_sign:                                    | N/A                                                   |
| `Succeeded`                                           | *bool*                                                | :heavy_check_mark:                                    | N/A                                                   |