# JobTypeResourceLimit

sets resource requirements for a specific job type for an actor definition. these values override the default, if both are set.


## Fields

| Field                                                                           | Type                                                                            | Required                                                                        | Description                                                                     |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| `JobType`                                                                       | [JobType](../../models/shared/jobtype.md)                                       | :heavy_check_mark:                                                              | enum that describes the different types of jobs that the platform runs.         |
| `ResourceRequirements`                                                          | [ResourceRequirements](../../models/shared/resourcerequirements.md)             | :heavy_check_mark:                                                              | optional resource requirements to run workers (blank for unbounded allocations) |