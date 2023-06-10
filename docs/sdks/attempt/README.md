# Attempt

## Overview

Interactions with attempt related resources.

### Available Operations

* [SaveStats](#savestats) - For worker to set sync stats of a running attempt.
* [SaveSyncConfig](#savesyncconfig) - For worker to save the AttemptSyncConfig for an attempt.
* [SetWorkflowInAttempt](#setworkflowinattempt) - For worker to register the workflow id in attempt.

## SaveStats

For worker to set sync stats of a running attempt.

### Example Usage

```go
package main

import(
	"context"
	"log"
	"airbyte-test"
	"airbyte-test/pkg/models/shared"
)

func main() {
    s := airbytetest.New()

    ctx := context.Background()
    res, err := s.Attempt.SaveStats(ctx, shared.SaveStatsRequestBody{
        AttemptNumber: 392785,
        JobID: 925597,
        Stats: shared.AttemptStats{
            BytesEmitted: airbytetest.Int64(836079),
            EstimatedBytes: airbytetest.Int64(71036),
            EstimatedRecords: airbytetest.Int64(337396),
            RecordsCommitted: airbytetest.Int64(87129),
            RecordsEmitted: airbytetest.Int64(648172),
            StateMessagesEmitted: airbytetest.Int64(20218),
        },
        StreamStats: []shared.AttemptStreamStats{
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(832620),
                    EstimatedBytes: airbytetest.Int64(957156),
                    EstimatedRecords: airbytetest.Int64(778157),
                    RecordsCommitted: airbytetest.Int64(140350),
                    RecordsEmitted: airbytetest.Int64(870013),
                    StateMessagesEmitted: airbytetest.Int64(870088),
                },
                StreamName: "maiores",
                StreamNamespace: airbytetest.String("molestiae"),
            },
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(799159),
                    EstimatedBytes: airbytetest.Int64(800911),
                    EstimatedRecords: airbytetest.Int64(461479),
                    RecordsCommitted: airbytetest.Int64(520478),
                    RecordsEmitted: airbytetest.Int64(780529),
                    StateMessagesEmitted: airbytetest.Int64(678880),
                },
                StreamName: "dicta",
                StreamNamespace: airbytetest.String("nam"),
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.InternalOperationResult != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                  | Type                                                                       | Required                                                                   | Description                                                                |
| -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| `ctx`                                                                      | [context.Context](https://pkg.go.dev/context#Context)                      | :heavy_check_mark:                                                         | The context to use for the request.                                        |
| `request`                                                                  | [shared.SaveStatsRequestBody](../../models/shared/savestatsrequestbody.md) | :heavy_check_mark:                                                         | The request object to use for the request.                                 |


### Response

**[*operations.SaveStatsResponse](../../models/operations/savestatsresponse.md), error**


## SaveSyncConfig

For worker to save the AttemptSyncConfig for an attempt.

### Example Usage

```go
package main

import(
	"context"
	"log"
	"airbyte-test"
	"airbyte-test/pkg/models/shared"
)

func main() {
    s := airbytetest.New()

    ctx := context.Background()
    res, err := s.Attempt.SaveSyncConfig(ctx, shared.SaveAttemptSyncConfigRequestBody{
        AttemptNumber: 639921,
        JobID: 582020,
        SyncConfig: shared.AttemptSyncConfig{
            DestinationConfiguration: "fugit",
            SourceConfiguration: "deleniti",
            State: &shared.ConnectionState{
                ConnectionID: "fc816742-cb73-4920-9929-396fea7596eb",
                GlobalState: &shared.GlobalState{
                    SharedState: &shared.StateBlob{},
                    StreamStates: []shared.StreamState{
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Lela Orn",
                                Namespace: airbytetest.String("dolores"),
                            },
                            StreamState: &shared.StateBlob{},
                        },
                    },
                },
                State: &shared.StateBlob{},
                StateType: shared.ConnectionStateTypeGlobal,
                StreamState: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Della Halvorson",
                            Namespace: airbytetest.String("minima"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Brian Kessler",
                            Namespace: airbytetest.String("sapiente"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                },
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.InternalOperationResult != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                          | Type                                                                                               | Required                                                                                           | Description                                                                                        |
| -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                              | :heavy_check_mark:                                                                                 | The context to use for the request.                                                                |
| `request`                                                                                          | [shared.SaveAttemptSyncConfigRequestBody](../../models/shared/saveattemptsyncconfigrequestbody.md) | :heavy_check_mark:                                                                                 | The request object to use for the request.                                                         |


### Response

**[*operations.SaveSyncConfigResponse](../../models/operations/savesyncconfigresponse.md), error**


## SetWorkflowInAttempt

For worker to register the workflow id in attempt.

### Example Usage

```go
package main

import(
	"context"
	"log"
	"airbyte-test"
	"airbyte-test/pkg/models/shared"
)

func main() {
    s := airbytetest.New()

    ctx := context.Background()
    res, err := s.Attempt.SetWorkflowInAttempt(ctx, shared.SetWorkflowInAttemptRequestBody{
        AttemptNumber: 102044,
        JobID: 652790,
        ProcessingTaskQueue: airbytetest.String("dolorem"),
        WorkflowID: "culpa",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.InternalOperationResult != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `request`                                                                                        | [shared.SetWorkflowInAttemptRequestBody](../../models/shared/setworkflowinattemptrequestbody.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |


### Response

**[*operations.SetWorkflowInAttemptResponse](../../models/operations/setworkflowinattemptresponse.md), error**

