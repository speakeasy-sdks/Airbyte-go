# AttemptFailureOrigin

Indicates where the error originated. If not set, the origin of error is not well known.


## Values

| Name                                  | Value                                 |
| ------------------------------------- | ------------------------------------- |
| `AttemptFailureOriginSource`          | source                                |
| `AttemptFailureOriginDestination`     | destination                           |
| `AttemptFailureOriginReplication`     | replication                           |
| `AttemptFailureOriginPersistence`     | persistence                           |
| `AttemptFailureOriginNormalization`   | normalization                         |
| `AttemptFailureOriginDbt`             | dbt                                   |
| `AttemptFailureOriginAirbytePlatform` | airbyte_platform                      |
| `AttemptFailureOriginUnknown`         | unknown                               |