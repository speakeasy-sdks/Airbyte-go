# Scheduler

### Available Operations

* [ExecuteDestinationCheckConnection](#executedestinationcheckconnection) - Run check connection for a given destination configuration
* [ExecuteSourceCheckConnection](#executesourcecheckconnection) - Run check connection for a given source configuration
* [ExecuteSourceDiscoverSchema](#executesourcediscoverschema) - Run discover schema for a given source a source configuration

## ExecuteDestinationCheckConnection

Run check connection for a given destination configuration

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
    res, err := s.Scheduler.ExecuteDestinationCheckConnection(ctx, shared.DestinationCoreConfig{
        ConnectionConfiguration: "ipsa",
        DestinationDefinitionID: "f5ae2f3a-6b70-4087-8756-143f5a6c98b5",
        DestinationID: airbytetest.String("5554080d-40bc-4acc-acbd-6b5f3ec90930"),
        WorkspaceID: "4f926bad-2553-4819-b474-b0ed20e56248",
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

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `ctx`                                                                        | [context.Context](https://pkg.go.dev/context#Context)                        | :heavy_check_mark:                                                           | The context to use for the request.                                          |
| `request`                                                                    | [shared.DestinationCoreConfig](../../models/shared/destinationcoreconfig.md) | :heavy_check_mark:                                                           | The request object to use for the request.                                   |


### Response

**[*operations.ExecuteDestinationCheckConnectionResponse](../../models/operations/executedestinationcheckconnectionresponse.md), error**


## ExecuteSourceCheckConnection

Run check connection for a given source configuration

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
    res, err := s.Scheduler.ExecuteSourceCheckConnection(ctx, shared.SourceCoreConfig{
        ConnectionConfiguration: "hic",
        SourceDefinitionID: "ff639a91-0abd-4cab-a267-6696e1ec0022",
        SourceID: airbytetest.String("1b335d89-acb3-4ecf-9a8d-0c549ef03004"),
        WorkspaceID: "978a61fa-1cf2-4068-8f77-c1ffc71dca16",
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

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.SourceCoreConfig](../../models/shared/sourcecoreconfig.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.ExecuteSourceCheckConnectionResponse](../../models/operations/executesourcecheckconnectionresponse.md), error**


## ExecuteSourceDiscoverSchema

Run discover schema for a given source a source configuration

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
    res, err := s.Scheduler.ExecuteSourceDiscoverSchema(ctx, shared.SourceCoreConfig{
        ConnectionConfiguration: "consectetur",
        SourceDefinitionID: "f2a3c80a-97ff-4334-8ddf-857a9e61876c",
        SourceID: airbytetest.String("6ab21d29-dfc9-44d6-becd-799390066a6d"),
        WorkspaceID: "2d000355-338c-4ec0-86fa-21e9152cb311",
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

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.SourceCoreConfig](../../models/shared/sourcecoreconfig.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.ExecuteSourceDiscoverSchemaResponse](../../models/operations/executesourcediscoverschemaresponse.md), error**

