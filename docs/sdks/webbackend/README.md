# WebBackend

## Overview

Endpoints for the Airbyte web application. Those APIs should not be called outside the web application implementation and are not
guaranteeing any backwards compatibility.


### Available Operations

* [GetStateType](#getstatetype) - Fetch the current state type for a connection.
* [WebBackendCheckUpdates](#webbackendcheckupdates) - Returns a summary of source and destination definitions that could be updated.
* [WebBackendCreateConnection](#webbackendcreateconnection) - Create a connection
* [WebBackendGetConnection](#webbackendgetconnection) - Get a connection
* [WebBackendGetWorkspaceState](#webbackendgetworkspacestate) - Returns the current state of a workspace
* [WebBackendListConnectionsForWorkspace](#webbackendlistconnectionsforworkspace) - Returns all non-deleted connections for a workspace.
* [WebBackendListGeographies](#webbackendlistgeographies) - Returns available geographies can be selected to run data syncs in a particular geography.
The 'auto' entry indicates that the sync will be automatically assigned to a geography according
to the platform default behavior. Entries other than 'auto' are two-letter country codes that
follow the ISO 3166-1 alpha-2 standard.

* [WebBackendUpdateConnection](#webbackendupdateconnection) - Update a connection

## GetStateType

Fetch the current state type for a connection.

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
    res, err := s.WebBackend.GetStateType(ctx, shared.ConnectionIDRequestBody{
        ConnectionID: "044f65fe-72dc-4407-bd0c-c3f408efc15c",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.ConnectionStateType != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `ctx`                                                                            | [context.Context](https://pkg.go.dev/context#Context)                            | :heavy_check_mark:                                                               | The context to use for the request.                                              |
| `request`                                                                        | [shared.ConnectionIDRequestBody](../../models/shared/connectionidrequestbody.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |


### Response

**[*operations.GetStateTypeResponse](../../models/operations/getstatetyperesponse.md), error**


## WebBackendCheckUpdates

Returns a summary of source and destination definitions that could be updated.

### Example Usage

```go
package main

import(
	"context"
	"log"
	"airbyte-test"
)

func main() {
    s := airbytetest.New()

    ctx := context.Background()
    res, err := s.WebBackend.WebBackendCheckUpdates(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendCheckUpdatesRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.WebBackendCheckUpdatesResponse](../../models/operations/webbackendcheckupdatesresponse.md), error**


## WebBackendCreateConnection

Create a connection

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
    res, err := s.WebBackend.WebBackendCreateConnection(ctx, shared.WebBackendConnectionCreate{
        DestinationID: "eb4d6e1e-ae0f-475a-adf2-acab58b991c9",
        Geography: shared.GeographyAuto.ToPointer(),
        Name: airbytetest.String("Mable Stroman"),
        NamespaceDefinition: shared.NamespaceDefinitionTypeDestination.ToPointer(),
        NamespaceFormat: airbytetest.String("${SOURCE_NAMESPACE}"),
        NonBreakingChangesPreference: shared.NonBreakingChangesPreferenceDisable.ToPointer(),
        OperationIds: []string{
            "61e7421c-be6d-4950-af0e-a930b69f7ac2",
            "f72f8850-0904-4911-a082-07888ec66183",
        },
        Operations: []shared.OperationCreate{
            shared.OperationCreate{
                Name: "Terence Mertz",
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("unde"),
                        DockerImage: airbytetest.String("debitis"),
                        GitRepoBranch: airbytetest.String("quidem"),
                        GitRepoURL: "magnam",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeNormalization,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 881095,
                            JobID: 800761,
                        },
                        ExecutionBody: airbytetest.String("sunt"),
                        ExecutionURL: airbytetest.String("voluptas"),
                        WebhookConfigID: airbytetest.String("faf75b0b-532a-44da-b7cb-aaf4452c4842"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "c9b2ad32-dafe-481a-88f4-444573fecd47",
            },
            shared.OperationCreate{
                Name: "Vivian Donnelly",
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("dolor"),
                        DockerImage: airbytetest.String("placeat"),
                        GitRepoBranch: airbytetest.String("quos"),
                        GitRepoURL: "sed",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeNormalization,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 617060,
                            JobID: 191202,
                        },
                        ExecutionBody: airbytetest.String("nihil"),
                        ExecutionURL: airbytetest.String("unde"),
                        WebhookConfigID: airbytetest.String("aa69cd5f-bcf7-49da-98a7-822bf95894e6"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "861adb55-f9e5-4d75-9c9f-e8f7502bfdc3",
            },
            shared.OperationCreate{
                Name: "Veronica Abshire",
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("illo"),
                        DockerImage: airbytetest.String("a"),
                        GitRepoBranch: airbytetest.String("et"),
                        GitRepoURL: "molestiae",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeDbt,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 294314,
                            JobID: 261219,
                        },
                        ExecutionBody: airbytetest.String("nostrum"),
                        ExecutionURL: airbytetest.String("ex"),
                        WebhookConfigID: airbytetest.String("379f3fb2-7e21-4f86-a657-b36fc6b9f587"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "ce525c67-641a-4831-ae50-47b4c21ccb42",
            },
        },
        Prefix: airbytetest.String("amet"),
        ResourceRequirements: &shared.ResourceRequirements{
            CPULimit: airbytetest.String("culpa"),
            CPURequest: airbytetest.String("facilis"),
            MemoryLimit: airbytetest.String("minus"),
            MemoryRequest: airbytetest.String("vero"),
        },
        Schedule: &shared.ConnectionSchedule{
            TimeUnit: shared.ConnectionScheduleTimeUnitWeeks,
            Units: 607242,
        },
        ScheduleData: &shared.ConnectionScheduleData{
            BasicSchedule: &shared.ConnectionScheduleDataBasicSchedule{
                TimeUnit: shared.ConnectionScheduleDataBasicScheduleTimeUnitMinutes,
                Units: 939131,
            },
            Cron: &shared.ConnectionScheduleDataCron{
                CronExpression: "fuga",
                CronTimeZone: "est",
            },
        },
        ScheduleType: shared.ConnectionScheduleTypeCron.ToPointer(),
        SourceCatalogID: airbytetest.String("dd88e71f-6c48-4252-9777-1e7fd074009e"),
        SourceID: "f8d29de1-dd70-497b-9da0-8c57fa6c78a2",
        Status: shared.ConnectionStatusActive,
        SyncCatalog: &shared.AirbyteCatalog{
            Streams: []shared.AirbyteStreamAndConfiguration{
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("accusamus"),
                        CursorField: []string{
                            "excepturi",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppendDedup,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "repudiandae",
                                "minus",
                                "officia",
                                "laboriosam",
                            },
                            []string{
                                "cupiditate",
                            },
                            []string{
                                "aliquam",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "dicta",
                                    "magnam",
                                    "doloremque",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "suscipit",
                                    "eius",
                                    "maiores",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "quos",
                                    "id",
                                    "officiis",
                                    "ab",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeFullRefresh,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "itaque",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Donald Ernser",
                        Namespace: airbytetest.String("a"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "recusandae",
                                "numquam",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeIncremental,
                            shared.SyncModeIncremental,
                            shared.SyncModeFullRefresh,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("quas"),
                        CursorField: []string{
                            "enim",
                            "corporis",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeOverwrite,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "voluptate",
                                "nesciunt",
                            },
                            []string{
                                "animi",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "temporibus",
                                    "porro",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "commodi",
                                    "autem",
                                    "praesentium",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "quisquam",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "eaque",
                            "delectus",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Kim Wiegand",
                        Namespace: airbytetest.String("a"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "earum",
                                "occaecati",
                            },
                            []string{
                                "quidem",
                            },
                            []string{
                                "laborum",
                                "molestias",
                                "a",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeFullRefresh,
                            shared.SyncModeIncremental,
                        },
                    },
                },
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendConnectionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ctx`                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                  | :heavy_check_mark:                                                                     | The context to use for the request.                                                    |
| `request`                                                                              | [shared.WebBackendConnectionCreate](../../models/shared/webbackendconnectioncreate.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |


### Response

**[*operations.WebBackendCreateConnectionResponse](../../models/operations/webbackendcreateconnectionresponse.md), error**


## WebBackendGetConnection

Get a connection

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
    res, err := s.WebBackend.WebBackendGetConnection(ctx, shared.WebBackendConnectionRequestBody{
        ConnectionID: "46e2c330-9db0-4536-99e7-5ca006f5392c",
        WithRefreshedCatalog: airbytetest.Bool(false),
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendConnectionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `request`                                                                                        | [shared.WebBackendConnectionRequestBody](../../models/shared/webbackendconnectionrequestbody.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |


### Response

**[*operations.WebBackendGetConnectionResponse](../../models/operations/webbackendgetconnectionresponse.md), error**


## WebBackendGetWorkspaceState

Returns the current state of a workspace

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
    res, err := s.WebBackend.WebBackendGetWorkspaceState(ctx, shared.WebBackendWorkspaceState{
        WorkspaceID: "11a25a8b-f92f-4974-a8ad-9a9f8bf82211",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendWorkspaceStateResult != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [shared.WebBackendWorkspaceState](../../models/shared/webbackendworkspacestate.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |


### Response

**[*operations.WebBackendGetWorkspaceStateResponse](../../models/operations/webbackendgetworkspacestateresponse.md), error**


## WebBackendListConnectionsForWorkspace

Returns all non-deleted connections for a workspace.

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
    res, err := s.WebBackend.WebBackendListConnectionsForWorkspace(ctx, shared.WebBackendConnectionListRequestBody{
        DestinationID: []string{
            "5359d983-87f7-4a79-8d72-cd2484da2172",
        },
        SourceID: []string{
            "f2ac41ef-5725-4f11-a9ac-1e41d8a23c23",
            "e34f2dfa-4a19-47f6-9e92-2151fe171209",
            "9853e9f5-43d8-4544-b9ee-224460443bc1",
        },
        WorkspaceID: "54188c2f-56e8-45da-b832-eabd617c3b0d",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendConnectionReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                | Type                                                                                                     | Required                                                                                                 | Description                                                                                              |
| -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                    | :heavy_check_mark:                                                                                       | The context to use for the request.                                                                      |
| `request`                                                                                                | [shared.WebBackendConnectionListRequestBody](../../models/shared/webbackendconnectionlistrequestbody.md) | :heavy_check_mark:                                                                                       | The request object to use for the request.                                                               |


### Response

**[*operations.WebBackendListConnectionsForWorkspaceResponse](../../models/operations/webbackendlistconnectionsforworkspaceresponse.md), error**


## WebBackendListGeographies

Returns all available geographies in which a data sync can run.

### Example Usage

```go
package main

import(
	"context"
	"log"
	"airbyte-test"
)

func main() {
    s := airbytetest.New()

    ctx := context.Background()
    res, err := s.WebBackend.WebBackendListGeographies(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendGeographiesListResult != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.WebBackendListGeographiesResponse](../../models/operations/webbackendlistgeographiesresponse.md), error**


## WebBackendUpdateConnection

Apply a patch-style update to a connection. Only fields present on the update request body will be updated.
Any operations that lack an ID will be created. Then, the newly created operationId will be applied to the
connection along with the rest of the operationIds in the request body.
Apply a patch-style update to a connection. Only fields present on the update request body will be updated.
Note that if a catalog is present in the request body, the connection's entire catalog will be replaced
with the catalog from the request. This means that to modify a single stream, the entire new catalog
containing the updated stream needs to be sent.


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
    res, err := s.WebBackend.WebBackendUpdateConnection(ctx, shared.WebBackendConnectionUpdate{
        ConnectionID: "51a44bf0-1bad-4870-ad46-082bfbdc41ff",
        Geography: shared.GeographyUs.ToPointer(),
        Name: airbytetest.String("Clifford Torp"),
        NamespaceDefinition: shared.NamespaceDefinitionTypeCustomformat.ToPointer(),
        NamespaceFormat: airbytetest.String("${SOURCE_NAMESPACE}"),
        NonBreakingChangesPreference: shared.NonBreakingChangesPreferenceIgnore.ToPointer(),
        NotifySchemaChanges: airbytetest.Bool(false),
        Operations: []shared.WebBackendOperationCreateOrUpdate{
            shared.WebBackendOperationCreateOrUpdate{
                Name: "Warren Rutherford",
                OperationID: airbytetest.String("5d17638f-1edb-4783-99ec-c5cb860f8cd5"),
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("praesentium"),
                        DockerImage: airbytetest.String("perferendis"),
                        GitRepoBranch: airbytetest.String("soluta"),
                        GitRepoURL: "animi",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeDbt,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 197872,
                            JobID: 559715,
                        },
                        ExecutionBody: airbytetest.String("sunt"),
                        ExecutionURL: airbytetest.String("aperiam"),
                        WebhookConfigID: airbytetest.String("e4fe4447-297c-4d3b-9dd3-bbce247b7684"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "eff50126-d71c-4ffb-90eb-74b8421953b4",
            },
            shared.WebBackendOperationCreateOrUpdate{
                Name: "Melody Stoltenberg",
                OperationID: airbytetest.String("43159d33-e595-43c0-8113-9863aa41e6c3"),
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("ab"),
                        DockerImage: airbytetest.String("maxime"),
                        GitRepoBranch: airbytetest.String("porro"),
                        GitRepoURL: "explicabo",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeWebhook,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 120600,
                            JobID: 942436,
                        },
                        ExecutionBody: airbytetest.String("porro"),
                        ExecutionURL: airbytetest.String("tempore"),
                        WebhookConfigID: airbytetest.String("51c9a41f-fbe9-4cbd-b95e-e65e076cc7ab"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "f616ea5c-7164-4193-8b90-f2e09d19d2fc",
            },
            shared.WebBackendOperationCreateOrUpdate{
                Name: "Faith Mosciski",
                OperationID: airbytetest.String("e105944b-935d-4237-a72f-90849d6aed4a"),
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("eveniet"),
                        DockerImage: airbytetest.String("optio"),
                        GitRepoBranch: airbytetest.String("soluta"),
                        GitRepoURL: "dignissimos",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeDbt,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 204877,
                            JobID: 458597,
                        },
                        ExecutionBody: airbytetest.String("placeat"),
                        ExecutionURL: airbytetest.String("at"),
                        WebhookConfigID: airbytetest.String("9222c9ff-5749-41aa-bfa2-e761f0ca4d45"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "6ef1031e-6899-4f0c-a001-e22cd55cc058",
            },
            shared.WebBackendOperationCreateOrUpdate{
                Name: "Hattie Botsford",
                OperationID: airbytetest.String("d76d971f-c820-4c65-b037-bb8e0cc88518"),
                OperatorConfiguration: shared.OperatorConfiguration{
                    Dbt: &shared.OperatorDbt{
                        DbtArguments: airbytetest.String("molestiae"),
                        DockerImage: airbytetest.String("officiis"),
                        GitRepoBranch: airbytetest.String("labore"),
                        GitRepoURL: "nulla",
                    },
                    Normalization: &shared.OperatorNormalization{
                        Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
                    },
                    OperatorType: shared.OperatorTypeWebhook,
                    Webhook: &shared.OperatorWebhook{
                        DbtCloud: &shared.OperatorWebhookDbtCloud{
                            AccountID: 9687,
                            JobID: 284927,
                        },
                        ExecutionBody: airbytetest.String("laborum"),
                        ExecutionURL: airbytetest.String("hic"),
                        WebhookConfigID: airbytetest.String("28c5dddb-46aa-41cf-96d8-28da01319112"),
                        WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
                    },
                },
                WorkspaceID: "9646645c-1d81-4f29-842f-569b7aff0ea2",
            },
        },
        Prefix: airbytetest.String("eos"),
        ResourceRequirements: &shared.ResourceRequirements{
            CPULimit: airbytetest.String("veritatis"),
            CPURequest: airbytetest.String("vel"),
            MemoryLimit: airbytetest.String("placeat"),
            MemoryRequest: airbytetest.String("libero"),
        },
        Schedule: &shared.ConnectionSchedule{
            TimeUnit: shared.ConnectionScheduleTimeUnitMonths,
            Units: 57719,
        },
        ScheduleData: &shared.ConnectionScheduleData{
            BasicSchedule: &shared.ConnectionScheduleDataBasicSchedule{
                TimeUnit: shared.ConnectionScheduleDataBasicScheduleTimeUnitDays,
                Units: 82503,
            },
            Cron: &shared.ConnectionScheduleDataCron{
                CronExpression: "harum",
                CronTimeZone: "cumque",
            },
        },
        ScheduleType: shared.ConnectionScheduleTypeManual.ToPointer(),
        SkipReset: airbytetest.Bool(false),
        SourceCatalogID: airbytetest.String("63e279a3-b084-4da9-9257-d04f40847a74"),
        Status: shared.ConnectionStatusActive.ToPointer(),
        SyncCatalog: &shared.AirbyteCatalog{
            Streams: []shared.AirbyteStreamAndConfiguration{
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("blanditiis"),
                        CursorField: []string{
                            "eius",
                            "cupiditate",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeOverwrite,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "facere",
                                "earum",
                                "debitis",
                            },
                            []string{
                                "reiciendis",
                                "ex",
                                "tempore",
                                "provident",
                            },
                            []string{
                                "soluta",
                                "maxime",
                                "commodi",
                            },
                            []string{
                                "corporis",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "eveniet",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "asperiores",
                                    "temporibus",
                                    "delectus",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeFullRefresh,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "porro",
                            "dolores",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Ms. Mario Sawayn DDS",
                        Namespace: airbytetest.String("accusantium"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "et",
                                "fugit",
                                "quos",
                            },
                            []string{
                                "voluptate",
                                "autem",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeIncremental,
                            shared.SyncModeIncremental,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("earum"),
                        CursorField: []string{
                            "assumenda",
                            "doloremque",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppendDedup,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "vel",
                                "itaque",
                                "nulla",
                                "excepturi",
                            },
                            []string{
                                "in",
                                "nesciunt",
                                "temporibus",
                                "temporibus",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "ut",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "dignissimos",
                                    "illo",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeFullRefresh,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "occaecati",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Nelson Walker",
                        Namespace: airbytetest.String("doloremque"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "minus",
                            },
                            []string{
                                "id",
                                "architecto",
                            },
                            []string{
                                "perspiciatis",
                                "quod",
                                "magni",
                                "incidunt",
                            },
                            []string{
                                "quisquam",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeIncremental,
                            shared.SyncModeFullRefresh,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("aliquid"),
                        CursorField: []string{
                            "illo",
                            "reiciendis",
                            "ipsum",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppend,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "non",
                                "facere",
                            },
                            []string{
                                "exercitationem",
                                "quidem",
                                "ea",
                                "molestiae",
                            },
                            []string{
                                "excepturi",
                            },
                            []string{
                                "iste",
                                "eaque",
                                "reiciendis",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "est",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "nobis",
                                    "expedita",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeFullRefresh,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "atque",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Jordan Hegmann",
                        Namespace: airbytetest.String("laboriosam"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "perspiciatis",
                                "dicta",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeFullRefresh,
                            shared.SyncModeFullRefresh,
                            shared.SyncModeFullRefresh,
                            shared.SyncModeIncremental,
                        },
                    },
                },
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("sequi"),
                        CursorField: []string{
                            "consequuntur",
                            "quae",
                            "veniam",
                            "sint",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppendDedup,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "nesciunt",
                                "maiores",
                                "veniam",
                                "autem",
                            },
                            []string{
                                "officiis",
                                "aperiam",
                            },
                            []string{
                                "sed",
                                "corporis",
                                "consequuntur",
                                "odio",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "nobis",
                                    "beatae",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "ex",
                                    "consequuntur",
                                    "delectus",
                                    "nobis",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "optio",
                            "debitis",
                            "architecto",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "David Casper III",
                        Namespace: airbytetest.String("quod"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "aspernatur",
                            },
                            []string{
                                "sint",
                            },
                            []string{
                                "deleniti",
                                "earum",
                                "consequuntur",
                                "enim",
                            },
                            []string{
                                "quibusdam",
                                "accusantium",
                                "nulla",
                                "inventore",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeIncremental,
                            shared.SyncModeIncremental,
                            shared.SyncModeFullRefresh,
                        },
                    },
                },
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WebBackendConnectionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ctx`                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                  | :heavy_check_mark:                                                                     | The context to use for the request.                                                    |
| `request`                                                                              | [shared.WebBackendConnectionUpdate](../../models/shared/webbackendconnectionupdate.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |


### Response

**[*operations.WebBackendUpdateConnectionResponse](../../models/operations/webbackendupdateconnectionresponse.md), error**

