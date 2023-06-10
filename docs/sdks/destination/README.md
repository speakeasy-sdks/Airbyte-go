# Destination

## Overview

Destination related resources.

### Available Operations

* [CheckConnectionToDestination](#checkconnectiontodestination) - Check connection to the destination
* [CheckConnectionToDestinationForUpdate](#checkconnectiontodestinationforupdate) - Check connection for a proposed update to a destination
* [CloneDestination](#clonedestination) - Clone destination
* [CreateDestination](#createdestination) - Create a destination
* [DeleteDestination](#deletedestination) - Delete the destination
* [GetDestination](#getdestination) - Get configured destination
* [ListDestinationsForWorkspace](#listdestinationsforworkspace) - List configured destinations for a workspace
* [SearchDestinations](#searchdestinations) - Search destinations
* [UpdateDestination](#updatedestination) - Update a destination

## CheckConnectionToDestination

Check connection to the destination

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
    res, err := s.Destination.CheckConnectionToDestination(ctx, shared.DestinationIDRequestBody{
        DestinationID: "7956f925-1a5a-49da-a60f-f57bfaad4f9e",
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

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [shared.DestinationIDRequestBody](../../models/shared/destinationidrequestbody.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |


### Response

**[*operations.CheckConnectionToDestinationResponse](../../models/operations/checkconnectiontodestinationresponse.md), error**


## CheckConnectionToDestinationForUpdate

Check connection for a proposed update to a destination

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
    res, err := s.Destination.CheckConnectionToDestinationForUpdate(ctx, shared.DestinationUpdate{
        ConnectionConfiguration: "sapiente",
        DestinationID: "c1b4512c-1032-4648-9c2f-615199ebfd0e",
        Name: "Cary Toy",
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

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `ctx`                                                                | [context.Context](https://pkg.go.dev/context#Context)                | :heavy_check_mark:                                                   | The context to use for the request.                                  |
| `request`                                                            | [shared.DestinationUpdate](../../models/shared/destinationupdate.md) | :heavy_check_mark:                                                   | The request object to use for the request.                           |


### Response

**[*operations.CheckConnectionToDestinationForUpdateResponse](../../models/operations/checkconnectiontodestinationforupdateresponse.md), error**


## CloneDestination

Clone destination

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
    res, err := s.Destination.CloneDestination(ctx, shared.DestinationCloneRequestBody{
        DestinationCloneID: "632ca3ae-d011-4799-a312-fde04771778f",
        DestinationConfiguration: &shared.DestinationCloneConfiguration{
            ConnectionConfiguration: airbytetest.String("reiciendis"),
            Name: airbytetest.String("Mr. Diane Stiedemann"),
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `ctx`                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                    | :heavy_check_mark:                                                                       | The context to use for the request.                                                      |
| `request`                                                                                | [shared.DestinationCloneRequestBody](../../models/shared/destinationclonerequestbody.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |


### Response

**[*operations.CloneDestinationResponse](../../models/operations/clonedestinationresponse.md), error**


## CreateDestination

Create a destination

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
    res, err := s.Destination.CreateDestination(ctx, shared.DestinationCreate{
        ConnectionConfiguration: "tempora",
        DestinationDefinitionID: "76360a15-db6a-4660-a59a-1adeaab5851d",
        Name: "Krista Jakubowski",
        WorkspaceID: "b08b6189-1baa-40fe-9ade-008e6f8c5f35",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `ctx`                                                                | [context.Context](https://pkg.go.dev/context#Context)                | :heavy_check_mark:                                                   | The context to use for the request.                                  |
| `request`                                                            | [shared.DestinationCreate](../../models/shared/destinationcreate.md) | :heavy_check_mark:                                                   | The request object to use for the request.                           |


### Response

**[*operations.CreateDestinationResponse](../../models/operations/createdestinationresponse.md), error**


## DeleteDestination

Delete the destination

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
    res, err := s.Destination.DeleteDestination(ctx, shared.DestinationIDRequestBody{
        DestinationID: "0d8cdb5a-3418-4143-8104-21813d5208ec",
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

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [shared.DestinationIDRequestBody](../../models/shared/destinationidrequestbody.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |


### Response

**[*operations.DeleteDestinationResponse](../../models/operations/deletedestinationresponse.md), error**


## GetDestination

Get configured destination

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
    res, err := s.Destination.GetDestination(ctx, shared.DestinationIDRequestBody{
        DestinationID: "e7e253b6-6845-41c6-86e2-05e16deab3fe",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [shared.DestinationIDRequestBody](../../models/shared/destinationidrequestbody.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |


### Response

**[*operations.GetDestinationResponse](../../models/operations/getdestinationresponse.md), error**


## ListDestinationsForWorkspace

List configured destinations for a workspace

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
    res, err := s.Destination.ListDestinationsForWorkspace(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "c9578a64-5842-473a-8418-d162309fb092",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationReadList != nil {
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

**[*operations.ListDestinationsForWorkspaceResponse](../../models/operations/listdestinationsforworkspaceresponse.md), error**


## SearchDestinations

Search destinations

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
    res, err := s.Destination.SearchDestinations(ctx, shared.DestinationSearch{
        ConnectionConfiguration: airbytetest.String("occaecati"),
        DestinationDefinitionID: airbytetest.String("921aefb9-f58c-44d8-ae68-e4be056013f5"),
        DestinationID: airbytetest.String("9da757a5-9ecf-4ef6-aef1-caa3383c2beb"),
        DestinationName: airbytetest.String("dolore"),
        Name: airbytetest.String("Colleen Dickinson"),
        WorkspaceID: airbytetest.String("c8d72f64-d1db-41f2-8431-0661e96349e1"),
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `ctx`                                                                | [context.Context](https://pkg.go.dev/context#Context)                | :heavy_check_mark:                                                   | The context to use for the request.                                  |
| `request`                                                            | [shared.DestinationSearch](../../models/shared/destinationsearch.md) | :heavy_check_mark:                                                   | The request object to use for the request.                           |


### Response

**[*operations.SearchDestinationsResponse](../../models/operations/searchdestinationsresponse.md), error**


## UpdateDestination

Update a destination

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
    res, err := s.Destination.UpdateDestination(ctx, shared.DestinationUpdate{
        ConnectionConfiguration: "impedit",
        DestinationID: "f9e06e3a-4370-400a-a6b6-bc9b8f759eac",
        Name: "Dana Ortiz",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                            | Type                                                                 | Required                                                             | Description                                                          |
| -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `ctx`                                                                | [context.Context](https://pkg.go.dev/context#Context)                | :heavy_check_mark:                                                   | The context to use for the request.                                  |
| `request`                                                            | [shared.DestinationUpdate](../../models/shared/destinationupdate.md) | :heavy_check_mark:                                                   | The request object to use for the request.                           |


### Response

**[*operations.UpdateDestinationResponse](../../models/operations/updatedestinationresponse.md), error**

