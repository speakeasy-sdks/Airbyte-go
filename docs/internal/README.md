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
        ConnectionID: "00dec001-ac80-42e2-ac09-ff8f0f816ff3",
        ConnectionState: shared.ConnectionState{
            ConnectionID: "477c13e9-02c1-4412-9b09-60a668151a47",
            GlobalState: &shared.GlobalState{
                SharedState: map[string]interface{}{
                    "deserunt": "delectus",
                },
                StreamStates: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Peggy Schneider",
                            Namespace: airbytetest.String("aliquam"),
                        },
                        StreamState: map[string]interface{}{
                            "maiores": "laudantium",
                            "velit": "reiciendis",
                            "amet": "nemo",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Adrienne White",
                            Namespace: airbytetest.String("aliquid"),
                        },
                        StreamState: map[string]interface{}{
                            "a": "nobis",
                            "perspiciatis": "accusantium",
                            "dicta": "minus",
                            "commodi": "eveniet",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Geoffrey Powlowski",
                            Namespace: airbytetest.String("fugit"),
                        },
                        StreamState: map[string]interface{}{
                            "sequi": "eligendi",
                            "asperiores": "esse",
                        },
                    },
                },
            },
            State: map[string]interface{}{
                "sint": "repellat",
                "a": "animi",
                "maiores": "itaque",
            },
            StateType: shared.ConnectionStateTypeEnumNotSet,
            StreamState: []shared.StreamState{
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Sheila Torphy",
                        Namespace: airbytetest.String("saepe"),
                    },
                    StreamState: map[string]interface{}{
                        "repudiandae": "accusantium",
                        "officia": "impedit",
                    },
                },
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Mattie Gibson",
                        Namespace: airbytetest.String("nobis"),
                    },
                    StreamState: map[string]interface{}{
                        "minus": "quia",
                        "magnam": "reprehenderit",
                        "quod": "quos",
                    },
                },
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Allen Kozey",
                        Namespace: airbytetest.String("modi"),
                    },
                    StreamState: map[string]interface{}{
                        "necessitatibus": "architecto",
                    },
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
        ID: 564627,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.AttemptNormalizationStatusReadList != nil {
        // handle response
    }
}
```

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
        AttemptNumber: 292177,
        JobID: 125811,
        Stats: shared.AttemptStats{
            BytesEmitted: airbytetest.Int64(982991),
            EstimatedBytes: airbytetest.Int64(205011),
            EstimatedRecords: airbytetest.Int64(139745),
            RecordsCommitted: airbytetest.Int64(936845),
            RecordsEmitted: airbytetest.Int64(330596),
            StateMessagesEmitted: airbytetest.Int64(373106),
        },
        StreamStats: []shared.AttemptStreamStats{
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(350387),
                    EstimatedBytes: airbytetest.Int64(331269),
                    EstimatedRecords: airbytetest.Int64(469994),
                    RecordsCommitted: airbytetest.Int64(320326),
                    RecordsEmitted: airbytetest.Int64(394161),
                    StateMessagesEmitted: airbytetest.Int64(946808),
                },
                StreamName: "quis",
                StreamNamespace: airbytetest.String("quibusdam"),
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
        AttemptNumber: 366480,
        JobID: 382764,
        SyncConfig: shared.AttemptSyncConfig{
            DestinationConfiguration: "pariatur",
            SourceConfiguration: "sit",
            State: &shared.ConnectionState{
                ConnectionID: "bd0af2df-e13d-4b4f-a2cb-a3f8941aebc0",
                GlobalState: &shared.GlobalState{
                    SharedState: map[string]interface{}{
                        "corrupti": "eaque",
                        "deserunt": "aliquid",
                        "excepturi": "magni",
                    },
                    StreamStates: []shared.StreamState{
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Rodney Prohaska",
                                Namespace: airbytetest.String("optio"),
                            },
                            StreamState: map[string]interface{}{
                                "minus": "quo",
                                "quos": "asperiores",
                                "voluptatum": "iste",
                                "corporis": "accusantium",
                            },
                        },
                        shared.StreamState{
                            StreamDescriptor: shared.StreamDescriptor{
                                Name: "Susan Wyman",
                                Namespace: airbytetest.String("possimus"),
                            },
                            StreamState: map[string]interface{}{
                                "pariatur": "vel",
                            },
                        },
                    },
                },
                State: map[string]interface{}{
                    "mollitia": "quae",
                    "quos": "aperiam",
                    "non": "voluptates",
                    "ad": "aliquam",
                },
                StateType: shared.ConnectionStateTypeEnumNotSet,
                StreamState: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Ebony Bode",
                            Namespace: airbytetest.String("est"),
                        },
                        StreamState: map[string]interface{}{
                            "aliquid": "consectetur",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Ian Legros",
                            Namespace: airbytetest.String("recusandae"),
                        },
                        StreamState: map[string]interface{}{
                            "blanditiis": "numquam",
                            "sequi": "voluptatum",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Olivia Boehm",
                            Namespace: airbytetest.String("quidem"),
                        },
                        StreamState: map[string]interface{}{
                            "porro": "deserunt",
                            "magni": "nihil",
                            "voluptas": "animi",
                        },
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
        AttemptNumber: 413780,
        JobID: 716,
        ProcessingTaskQueue: airbytetest.String("fuga"),
        WorkflowID: "aut",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.InternalOperationResult != nil {
        // handle response
    }
}
```

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
                        AliasName: airbytetest.String("maxime"),
                        CursorField: []string{
                            "iste",
                            "ullam",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeEnumAppendDedup,
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
                        SyncMode: shared.SyncModeEnumIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "labore",
                            "expedita",
                            "corrupti",
                            "rem",
                        },
                        JSONSchema: map[string]interface{}{
                            "officiis": "cum",
                            "pariatur": "sapiente",
                            "quo": "incidunt",
                        },
                        Name: "Kim Sauer",
                        Namespace: airbytetest.String("occaecati"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "esse",
                                "hic",
                                "maxime",
                                "accusantium",
                            },
                            []string{
                                "fugit",
                                "pariatur",
                                "eligendi",
                            },
                            []string{
                                "veritatis",
                                "aut",
                                "laudantium",
                                "iusto",
                            },
                        },
                        SupportedSyncModes: []shared.SyncModeEnum{
                            shared.SyncModeEnumIncremental,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("tempora"),
                        CursorField: []string{
                            "rerum",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeEnumAppend,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "at",
                                "eum",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "blanditiis",
                                    "nihil",
                                    "atque",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "deserunt",
                                    "atque",
                                    "nostrum",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeEnumIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "est",
                        },
                        JSONSchema: map[string]interface{}{
                            "rem": "magni",
                            "quae": "quas",
                        },
                        Name: "Lloyd Grant",
                        Namespace: airbytetest.String("delectus"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "cumque",
                                "natus",
                                "quaerat",
                            },
                            []string{
                                "quia",
                                "officiis",
                                "mollitia",
                                "cumque",
                            },
                            []string{
                                "enim",
                                "eum",
                            },
                        },
                        SupportedSyncModes: []shared.SyncModeEnum{
                            shared.SyncModeEnumIncremental,
                            shared.SyncModeEnumFullRefresh,
                        },
                    },
                },
            },
        },
        ConfigurationHash: airbytetest.String("sit"),
        ConnectorVersion: airbytetest.String("odio"),
        SourceID: airbytetest.String("cfee8120-6e28-413f-a4a4-1c480d3f2132"),
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DiscoverCatalogResult != nil {
        // handle response
    }
}
```
