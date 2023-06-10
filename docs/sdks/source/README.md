# Source

## Overview

Source related resources.

### Available Operations

* [CheckConnectionToSource](#checkconnectiontosource) - Check connection to the source
* [CheckConnectionToSourceForUpdate](#checkconnectiontosourceforupdate) - Check connection for a proposed update to a source
* [CloneSource](#clonesource) - Clone source
* [CreateSource](#createsource) - Create a source
* [DeleteSource](#deletesource) - Delete a source
* [DiscoverSchemaForSource](#discoverschemaforsource) - Discover the schema catalog of the source
* [GetMostRecentSourceActorCatalog](#getmostrecentsourceactorcatalog) - Get most recent ActorCatalog for source
* [GetSource](#getsource) - Get source
* [ListSourcesForWorkspace](#listsourcesforworkspace) - List sources for workspace
* [SearchSources](#searchsources) - Search sources
* [UpdateSource](#updatesource) - Update a source
* [WriteDiscoverCatalogResult](#writediscovercatalogresult) - Should only called from worker, to write result from discover activity back to DB.

## CheckConnectionToSource

Check connection to the source

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
    res, err := s.Source.CheckConnectionToSource(ctx, shared.SourceIDRequestBody{
        SourceID: "9167b8e3-c8db-4034-88d6-d364ffd45590",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.CheckConnectionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [shared.SourceIDRequestBody](../../models/shared/sourceidrequestbody.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |


### Response

**[*operations.CheckConnectionToSourceResponse](../../models/operations/checkconnectiontosourceresponse.md), error**


## CheckConnectionToSourceForUpdate

Check connection for a proposed update to a source

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
    res, err := s.Source.CheckConnectionToSourceForUpdate(ctx, shared.SourceUpdate{
        ConnectionConfiguration: "ex",
        Name: "Keith Crist",
        SourceID: "d48e935c-2c9e-481f-b0be-3e43202d7216",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.CheckConnectionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `ctx`                                                      | [context.Context](https://pkg.go.dev/context#Context)      | :heavy_check_mark:                                         | The context to use for the request.                        |
| `request`                                                  | [shared.SourceUpdate](../../models/shared/sourceupdate.md) | :heavy_check_mark:                                         | The request object to use for the request.                 |


### Response

**[*operations.CheckConnectionToSourceForUpdateResponse](../../models/operations/checkconnectiontosourceforupdateresponse.md), error**


## CloneSource

Clone source

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
    res, err := s.Source.CloneSource(ctx, shared.SourceCloneRequestBody{
        SourceCloneID: "57650664-1870-4d9d-a1f9-ad030c4ecc11",
        SourceConfiguration: &shared.SourceCloneConfiguration{
            ConnectionConfiguration: airbytetest.String("id"),
            Name: airbytetest.String("Brandy Dicki"),
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.SourceCloneRequestBody](../../models/shared/sourceclonerequestbody.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |


### Response

**[*operations.CloneSourceResponse](../../models/operations/clonesourceresponse.md), error**


## CreateSource

Create a source

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
    res, err := s.Source.CreateSource(ctx, shared.SourceCreate{
        ConnectionConfiguration: "eos",
        Name: "Kenneth Hoppe",
        SourceDefinitionID: "8502a55e-7f73-4bc8-85e3-20a319f4badf",
        WorkspaceID: "947c9a86-7bc4-4242-a665-816ddca8ef51",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `ctx`                                                      | [context.Context](https://pkg.go.dev/context#Context)      | :heavy_check_mark:                                         | The context to use for the request.                        |
| `request`                                                  | [shared.SourceCreate](../../models/shared/sourcecreate.md) | :heavy_check_mark:                                         | The request object to use for the request.                 |


### Response

**[*operations.CreateSourceResponse](../../models/operations/createsourceresponse.md), error**


## DeleteSource

Delete a source

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
    res, err := s.Source.DeleteSource(ctx, shared.SourceIDRequestBody{
        SourceID: "fcb4c593-ec12-4cda-ad0e-c7afedbd80df",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.StatusCode == http.StatusOK {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [shared.SourceIDRequestBody](../../models/shared/sourceidrequestbody.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |


### Response

**[*operations.DeleteSourceResponse](../../models/operations/deletesourceresponse.md), error**


## DiscoverSchemaForSource

Discover the schema catalog of the source

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
    res, err := s.Source.DiscoverSchemaForSource(ctx, shared.SourceDiscoverSchemaRequestBody{
        ConnectionID: airbytetest.String("448a47f9-390c-4588-8098-3dabf9ef3ffd"),
        DisableCache: airbytetest.Bool(false),
        NotifySchemaChange: airbytetest.Bool(false),
        SourceID: "d9f7f079-af4d-4357-a4cd-b0f4d281187d",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDiscoverSchemaRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `request`                                                                                        | [shared.SourceDiscoverSchemaRequestBody](../../models/shared/sourcediscoverschemarequestbody.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |


### Response

**[*operations.DiscoverSchemaForSourceResponse](../../models/operations/discoverschemaforsourceresponse.md), error**


## GetMostRecentSourceActorCatalog

Get most recent ActorCatalog for source

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
    res, err := s.Source.GetMostRecentSourceActorCatalog(ctx, shared.SourceIDRequestBody{
        SourceID: "56844ede-d85a-4906-9e62-8bdfc2032b6c",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.ActorCatalogWithUpdatedAt != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [shared.SourceIDRequestBody](../../models/shared/sourceidrequestbody.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |


### Response

**[*operations.GetMostRecentSourceActorCatalogResponse](../../models/operations/getmostrecentsourceactorcatalogresponse.md), error**


## GetSource

Get source

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
    res, err := s.Source.GetSource(ctx, shared.SourceIDRequestBody{
        SourceID: "879923b7-e135-484f-bae1-2c6891f82ce1",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [shared.SourceIDRequestBody](../../models/shared/sourceidrequestbody.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |


### Response

**[*operations.GetSourceResponse](../../models/operations/getsourceresponse.md), error**


## ListSourcesForWorkspace

List sources for workspace. Does not return deleted sources.

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
    res, err := s.Source.ListSourcesForWorkspace(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "15717230-5377-4dcf-a89d-f975e3566860",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.WorkspaceIDRequestBody](../../models/shared/workspaceidrequestbody.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |


### Response

**[*operations.ListSourcesForWorkspaceResponse](../../models/operations/listsourcesforworkspaceresponse.md), error**


## SearchSources

Search sources

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
    res, err := s.Source.SearchSources(ctx, shared.SourceSearch{
        ConnectionConfiguration: airbytetest.String("perspiciatis"),
        Name: airbytetest.String("Kellie Miller"),
        SourceDefinitionID: airbytetest.String("ddc5f111-dea1-4026-9541-a4d190feb217"),
        SourceID: airbytetest.String("80bccc0d-bbdd-4b48-8708-fb4e391e6bc1"),
        SourceName: airbytetest.String("ad"),
        WorkspaceID: airbytetest.String("8c4c4e54-599e-4a34-a260-e9b200ce78a1"),
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `ctx`                                                      | [context.Context](https://pkg.go.dev/context#Context)      | :heavy_check_mark:                                         | The context to use for the request.                        |
| `request`                                                  | [shared.SourceSearch](../../models/shared/sourcesearch.md) | :heavy_check_mark:                                         | The request object to use for the request.                 |


### Response

**[*operations.SearchSourcesResponse](../../models/operations/searchsourcesresponse.md), error**


## UpdateSource

Update a source

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
    res, err := s.Source.UpdateSource(ctx, shared.SourceUpdate{
        ConnectionConfiguration: "expedita",
        Name: "Isaac Wyman",
        SourceID: "a0a116ce-723d-4409-bfa3-0e9af725b291",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `ctx`                                                      | [context.Context](https://pkg.go.dev/context#Context)      | :heavy_check_mark:                                         | The context to use for the request.                        |
| `request`                                                  | [shared.SourceUpdate](../../models/shared/sourceupdate.md) | :heavy_check_mark:                                         | The request object to use for the request.                 |


### Response

**[*operations.UpdateSourceResponse](../../models/operations/updatesourceresponse.md), error**


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
    res, err := s.Source.WriteDiscoverCatalogResult(ctx, shared.SourceDiscoverSchemaWriteRequestBody{
        Catalog: shared.AirbyteCatalog{
            Streams: []shared.AirbyteStreamAndConfiguration{
                shared.AirbyteStreamAndConfiguration{
                    Config: &shared.AirbyteStreamConfiguration{
                        AliasName: airbytetest.String("explicabo"),
                        CursorField: []string{
                            "amet",
                        },
                        DestinationSyncMode: shared.DestinationSyncModeAppend,
                        FieldSelectionEnabled: airbytetest.Bool(false),
                        PrimaryKey: [][]string{
                            []string{
                                "velit",
                                "hic",
                                "ullam",
                            },
                            []string{
                                "itaque",
                                "distinctio",
                                "iusto",
                            },
                            []string{
                                "provident",
                                "occaecati",
                            },
                            []string{
                                "sunt",
                                "odit",
                                "vero",
                                "deleniti",
                            },
                        },
                        Selected: airbytetest.Bool(false),
                        SelectedFields: []shared.SelectedFieldInfo{
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "repellat",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "magnam",
                                    "perspiciatis",
                                    "amet",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "sunt",
                                    "nemo",
                                    "delectus",
                                },
                            },
                            shared.SelectedFieldInfo{
                                FieldPath: []string{
                                    "porro",
                                    "quaerat",
                                    "magni",
                                    "cumque",
                                },
                            },
                        },
                        Suggested: airbytetest.Bool(false),
                        SyncMode: shared.SyncModeIncremental,
                    },
                    Stream: &shared.AirbyteStream{
                        DefaultCursorField: []string{
                            "commodi",
                            "maxime",
                        },
                        JSONSchema: &shared.StreamJSONSchema{},
                        Name: "Alexandra Crooks",
                        Namespace: airbytetest.String("harum"),
                        SourceDefinedCursor: airbytetest.Bool(false),
                        SourceDefinedPrimaryKey: [][]string{
                            []string{
                                "hic",
                                "quo",
                                "illo",
                                "nobis",
                            },
                            []string{
                                "nisi",
                                "explicabo",
                            },
                        },
                        SupportedSyncModes: []shared.SyncMode{
                            shared.SyncModeFullRefresh,
                        },
                    },
                },
            },
        },
        ConfigurationHash: airbytetest.String("reiciendis"),
        ConnectorVersion: airbytetest.String("quos"),
        SourceID: airbytetest.String("41fb1bd2-3fdb-414d-b6be-5a685998e22a"),
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

