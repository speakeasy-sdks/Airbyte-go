# SaveStatsRequestBody


## Fields

| Field                                                             | Type                                                              | Required                                                          | Description                                                       |
| ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------- |
| `AttemptNumber`                                                   | *int*                                                             | :heavy_check_mark:                                                | N/A                                                               |
| `JobID`                                                           | *int64*                                                           | :heavy_check_mark:                                                | N/A                                                               |
| `Stats`                                                           | [AttemptStats](../../models/shared/attemptstats.md)               | :heavy_check_mark:                                                | N/A                                                               |
| `StreamStats`                                                     | [][AttemptStreamStats](../../models/shared/attemptstreamstats.md) | :heavy_minus_sign:                                                | N/A                                                               |