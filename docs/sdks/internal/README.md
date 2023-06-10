# Internal

### Available Operations

* [CreateOrUpdateState](#createorupdatestate) - Create or update the state for a connection.
* [GetAttemptNormalizationStatusesForJob](#getattemptnormalizationstatusesforjob) - Get normalization status to determine if we can bypass normalization phase
* [SaveStats](#savestats) - For worker to set sync stats of a running attempt.
* [SaveSyncConfig](#savesyncconfig) - For worker to save the AttemptSyncConfig for an attempt.
* [SetWorkflowInAttempt](#setworkflowinattempt) - For worker to register the workflow id in attempt.
* [WriteDiscoverCatalogResult](#writediscovercatalogresult) - Should only called from worker, to write result from discover activity back to DB.

## CreateOrUpdateState

Create or update the state for a connection.

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
    res, err := s.Internal.CreateOrUpdateState(ctx, shared.ConnectionStateCreateOrUpdate{
        ConnectionID: "0019c6dc-5e34-4762-b99b-fbbe6949fb2b",
        ConnectionState: shared.ConnectionState{
            ConnectionID: "b4ecae6c-3d5d-4b3a-9ebd-5daea4c506a8",
            GlobalState: &shared.GlobalState{
                SharedState: &shared.StateBlob{},
                StreamStates: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Sergio Grant Sr.",
                            Namespace: airbytetest.String("aliquid"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Gail Roob",
                            Namespace: airbytetest.String("officiis"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Drew Mraz",
                            Namespace: airbytetest.String("nostrum"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                },
            },
            State: &shared.StateBlob{},
            StateType: shared.ConnectionStateTypeStream,
            StreamState: []shared.StreamState{
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Miss Carroll Rutherford",
                        Namespace: airbytetest.String("laboriosam"),
                    },
                    StreamState: &shared.StateBlob{},
                },
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Sandra Schumm",
                        Namespace: airbytetest.String("consequatur"),
                    },
                    StreamState: &shared.StateBlob{},
                },
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Julie Murazik",
                        Namespace: airbytetest.String("quae"),
                    },
                    StreamState: &shared.StateBlob{},
                },
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.ConnectionState != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                    | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `ctx`                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                        | :heavy_check_mark:                                                                           | The context to use for the request.                                                          |
| `request`                                                                                    | [shared.ConnectionStateCreateOrUpdate](../../models/shared/connectionstatecreateorupdate.md) | :heavy_check_mark:                                                                           | The request object to use for the request.                                                   |


### Response

**[*operations.CreateOrUpdateStateResponse](../../models/operations/createorupdatestateresponse.md), error**


## GetAttemptNormalizationStatusesForJob

Get normalization status to determine if we can bypass normalization phase

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
    res, err := s.Internal.GetAttemptNormalizationStatusesForJob(ctx, shared.JobIDRequestBody{
        ID: 169819,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.AttemptNormalizationStatusReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.JobIDRequestBody](../../models/shared/jobidrequestbody.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.GetAttemptNormalizationStatusesForJobResponse](../../models/operations/getattemptnormalizationstatusesforjobresponse.md), error**


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
    res, err := s.Internal.SaveStats(ctx, shared.SaveStatsRequestBody{
        AttemptNumber: 885797,
        JobID: 148379,
        Stats: shared.AttemptStats{
            BytesEmitted: airbytetest.Int64(898111),
            EstimatedBytes: airbytetest.Int64(773259),
            EstimatedRecords: airbytetest.Int64(55981),
            RecordsCommitted: airbytetest.Int64(567693),
            RecordsEmitted: airbytetest.Int64(950956),
            StateMessagesEmitted: airbytetest.Int64(983000),
        },
        StreamStats: []shared.AttemptStreamStats{
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(982248),
                    EstimatedBytes: airbytetest.Int64(691),
                    EstimatedRecords: airbytetest.Int64(992667),
                    RecordsCommitted: airbytetest.Int64(523365),
                    RecordsEmitted: airbytetest.Int64(118615),
                    StateMessagesEmitted: airbytetest.Int64(380595),
                },
                StreamName: "earum",
                StreamNamespace: airbytetest.String("doloribus"),
            },
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(244569),
                    EstimatedBytes: airbytetest.Int64(260588),
                    EstimatedRecords: airbytetest.Int64(458212),
                    RecordsCommitted: airbytetest.Int64(446547),
                    RecordsEmitted: airbytetest.Int64(757407),
                    StateMessagesEmitted: airbytetest.Int64(94697),
                },
                StreamName: "neque",
                StreamNamespace: airbytetest.String("vero"),
            },
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(566312),
                    EstimatedBytes: airbytetest.Int64(37534),
                    EstimatedRecords: airbytetest.Int64(185816),
                    RecordsCommitted: airbytetest.Int64(771241),
                    RecordsEmitted: airbytetest.Int64(104736),
                    StateMessagesEmitted: airbytetest.Int64(278329),
                },
                StreamName: "dicta",
                StreamNamespace: airbytetest.String("odit"),
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
    res, err := s.Internal.SaveSyncConfig(ctx, shared.SaveAttemptSyncConfigRequestBody{
        AttemptNumber: 357639,
        JobID: 701441,
        SyncConfig: shared.AttemptSyncConfig{
            DestinationConfiguration: "alias",
            SourceConfiguration: "error",
            State: &shared.ConnectionState{
                ConnectionID: "60a66815-1a47-42af-923c-5949f83f350c",
                GlobalState: &shared.GlobalState{
                    SharedState: &shared.StateBlob{},
                    StreamStates: []shared.StreamState{
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Clinton Hyatt",
                                Namespace: airbytetest.String("nobis"),
                            },
                            StreamState: &shared.StateBlob{},
                        },
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Steven Carter",
                                Namespace: airbytetest.String("eveniet"),
                            },
                            StreamState: &shared.StateBlob{},
                        },
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Geoffrey Powlowski",
                                Namespace: airbytetest.String("fugit"),
                            },
                            StreamState: &shared.StateBlob{},
                        },
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Lillian Rosenbaum",
                                Namespace: airbytetest.String("blanditiis"),
                            },
                            StreamState: &shared.StateBlob{},
                        },
                    },
                },
                State: &shared.StateBlob{},
                StateType: shared.ConnectionStateTypeLegacy,
                StreamState: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Lynn Wuckert",
                            Namespace: airbytetest.String("deserunt"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Sheila Torphy",
                            Namespace: airbytetest.String("saepe"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Delia Barton",
                            Namespace: airbytetest.String("quasi"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Frederick Schaden",
                            Namespace: airbytetest.String("natus"),
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
    res, err := s.Internal.SetWorkflowInAttempt(ctx, shared.SetWorkflowInAttemptRequestBody{
        AttemptNumber: 793568,
        JobID: 154389,
        ProcessingTaskQueue: airbytetest.String("magnam"),
        WorkflowID: "reprehenderit",
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


## WriteDiscoverCatalogResult

Should only called from worker, to write result from discover activity back to DB.

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
    res, err := s.Internal.WriteDiscoverCatalogResult(ctx, shared.SourceDiscoverSchemaWriteRequestBody{
        Catalog: shared.AirbyteCatalog{
            Streams: []shared.AirbyteStreamAndConfiguration{
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("quos"),
                        CursorField: []string{
                            "amet",
                            "molestiae",
                            "amet",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppendDedup,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "necessitatibus",
                            },
                            []string{
                                "molestias",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "maiores",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "odit",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "ipsam",
                            "eaque",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Lynn Kovacek",
                        Namespace: airbytetest.String("tenetur"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "nemo",
                                "suscipit",
                                "pariatur",
                                "sit",
                            },
                            []string{
                                "repellendus",
                                "perferendis",
                                "id",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeFullRefresh,
                            shared.SyncModeIncremental,
                            shared.SyncModeIncremental,
                            shared.SyncModeIncremental,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("architecto"),
                        CursorField: []string{
                            "pariatur",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppendDedup,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "iure",
                                "explicabo",
                                "minus",
                                "soluta",
                            },
                            []string{
                                "velit",
                                "earum",
                                "praesentium",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "quasi",
                                    "mollitia",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "harum",
                                    "cumque",
                                    "doloremque",
                                    "expedita",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "eaque",
                                    "deserunt",
                                    "aliquid",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "tempora",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Rodney Prohaska",
                        Namespace: airbytetest.String("optio"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "quo",
                                "quos",
                                "asperiores",
                                "voluptatum",
                            },
                            []string{
                                "corporis",
                                "accusantium",
                                "illo",
                            },
                            []string{
                                "doloribus",
                            },
                            []string{
                                "at",
                                "possimus",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeIncremental,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("vel"),
                        CursorField: []string{
                            "mollitia",
                            "quae",
                            "quos",
                            "aperiam",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppend,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "aliquam",
                                "quisquam",
                            },
                            []string{
                                "consequuntur",
                                "maiores",
                                "inventore",
                            },
                            []string{
                                "laudantium",
                                "est",
                            },
                            []string{
                                "aliquid",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "rem",
                                    "voluptatum",
                                    "ducimus",
                                    "adipisci",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "blanditiis",
                            "numquam",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Margie Balistreri DVM",
                        Namespace: airbytetest.String("autem"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "porro",
                                "deserunt",
                                "magni",
                            },
                            []string{
                                "voluptas",
                                "animi",
                            },
                            []string{
                                "alias",
                                "fuga",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeFullRefresh,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("maxime"),
                        CursorField: []string{
                            "iste",
                            "ullam",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppendDedup,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "occaecati",
                                "unde",
                            },
                            []string{
                                "nihil",
                            },
                            []string{
                                "libero",
                            },
                            []string{
                                "quasi",
                                "cumque",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "facere",
                                    "facilis",
                                    "beatae",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "labore",
                            "expedita",
                            "corrupti",
                            "rem",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Frankie Ritchie",
                        Namespace: airbytetest.String("quo"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "minus",
                                "porro",
                                "id",
                                "excepturi",
                            },
                            []string{
                                "libero",
                                "quo",
                                "esse",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeIncremental,
                            shared.SyncModeFullRefresh,
                            shared.SyncModeIncremental,
                            shared.SyncModeFullRefresh,
                        },
                    },
                },
            },
        },
        ConfigurationHash: airbytetest.String("pariatur"),
        ConnectorVersion: airbytetest.String("eligendi"),
        SourceID: airbytetest.String("e10873e4-2b00-46d6-b887-8ba8581a5820"),
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DiscoverCatalogResult != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                  | Type                                                                                                       | Required                                                                                                   | Description                                                                                                |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                                      | :heavy_check_mark:                                                                                         | The context to use for the request.                                                                        |
| `request`                                                                                                  | [shared.SourceDiscoverSchemaWriteRequestBody](../../models/shared/sourcediscoverschemawriterequestbody.md) | :heavy_check_mark:                                                                                         | The request object to use for the request.                                                                 |


### Response

**[*operations.WriteDiscoverCatalogResultResponse](../../models/operations/writediscovercatalogresultresponse.md), error**

