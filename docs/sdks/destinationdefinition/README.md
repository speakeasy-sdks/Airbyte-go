# DestinationDefinition

## Overview

DestinationDefinition related resources.

### Available Operations

* [CreateCustomDestinationDefinition](#createcustomdestinationdefinition) - Creates a custom destinationDefinition for the given workspace
* [DeleteDestinationDefinition](#deletedestinationdefinition) - Delete a destination definition
* [GetDestinationDefinition](#getdestinationdefinition) - Get destinationDefinition
* [GetDestinationDefinitionForWorkspace](#getdestinationdefinitionforworkspace) - Get a destinationDefinition that is configured for the given workspace
* [GrantDestinationDefinitionToWorkspace](#grantdestinationdefinitiontoworkspace) - grant a private, non-custom destinationDefinition to a given workspace
* [ListDestinationDefinitions](#listdestinationdefinitions) - List all the destinationDefinitions the current Airbyte deployment is configured to use
* [ListDestinationDefinitionsForWorkspace](#listdestinationdefinitionsforworkspace) - List all the destinationDefinitions the given workspace is configured to use
* [ListLatestDestinationDefinitions](#listlatestdestinationdefinitions) - List the latest destinationDefinitions Airbyte supports
* [ListPrivateDestinationDefinitions](#listprivatedestinationdefinitions) - List all private, non-custom destinationDefinitions, and for each indicate whether the given workspace has a grant for using the definition. Used by admins to view and modify a given workspace's grants.
* [RevokeDestinationDefinitionFromWorkspace](#revokedestinationdefinitionfromworkspace) - revoke a grant to a private, non-custom destinationDefinition from a given workspace
* [UpdateDestinationDefinition](#updatedestinationdefinition) - Update destinationDefinition

## CreateCustomDestinationDefinition

Creates a custom destinationDefinition for the given workspace

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
    res, err := s.DestinationDefinition.CreateCustomDestinationDefinition(ctx, shared.CustomDestinationDefinitionCreate{
        DestinationDefinition: shared.DestinationDefinitionCreate{
            DockerImageTag: "labore",
            DockerRepository: "veritatis",
            DocumentationURL: "https://empty-buffer.com",
            Icon: airbytetest.String("dolorem"),
            Name: "Tina Moore",
            ResourceRequirements: &shared.ActorDefinitionResourceRequirements{
                Default: &shared.ResourceRequirements{
                    CPULimit: airbytetest.String("soluta"),
                    CPURequest: airbytetest.String("libero"),
                    MemoryLimit: airbytetest.String("rem"),
                    MemoryRequest: airbytetest.String("dolorum"),
                },
                JobSpecific: []shared.JobTypeResourceLimit{
                    shared.JobTypeResourceLimit{
                        JobType: shared.JobTypeCheckConnection,
                        ResourceRequirements: shared.ResourceRequirements{
                            CPULimit: airbytetest.String("alias"),
                            CPURequest: airbytetest.String("magni"),
                            MemoryLimit: airbytetest.String("vel"),
                            MemoryRequest: airbytetest.String("quae"),
                        },
                    },
                    shared.JobTypeResourceLimit{
                        JobType: shared.JobTypeGetSpec,
                        ResourceRequirements: shared.ResourceRequirements{
                            CPULimit: airbytetest.String("modi"),
                            CPURequest: airbytetest.String("neque"),
                            MemoryLimit: airbytetest.String("exercitationem"),
                            MemoryRequest: airbytetest.String("itaque"),
                        },
                    },
                },
            },
        },
        WorkspaceID: "139dbc22-59b1-4abd-a8c0-70e1084cb067",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                | :heavy_check_mark:                                                                                   | The context to use for the request.                                                                  |
| `request`                                                                                            | [shared.CustomDestinationDefinitionCreate](../../models/shared/customdestinationdefinitioncreate.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |


### Response

**[*operations.CreateCustomDestinationDefinitionResponse](../../models/operations/createcustomdestinationdefinitionresponse.md), error**


## DeleteDestinationDefinition

Delete a destination definition

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
    res, err := s.DestinationDefinition.DeleteDestinationDefinition(ctx, shared.DestinationDefinitionIDRequestBody{
        DestinationDefinitionID: "2d1ad879-eeb9-4665-b85e-fbd02bae0be2",
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

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `request`                                                                                              | [shared.DestinationDefinitionIDRequestBody](../../models/shared/destinationdefinitionidrequestbody.md) | :heavy_check_mark:                                                                                     | The request object to use for the request.                                                             |


### Response

**[*operations.DeleteDestinationDefinitionResponse](../../models/operations/deletedestinationdefinitionresponse.md), error**


## GetDestinationDefinition

Get destinationDefinition

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
    res, err := s.DestinationDefinition.GetDestinationDefinition(ctx, shared.DestinationDefinitionIDRequestBody{
        DestinationDefinitionID: "d782259e-3ea4-4b51-97f9-2443da7ce52b",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                              | Type                                                                                                   | Required                                                                                               | Description                                                                                            |
| ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                                  | :heavy_check_mark:                                                                                     | The context to use for the request.                                                                    |
| `request`                                                                                              | [shared.DestinationDefinitionIDRequestBody](../../models/shared/destinationdefinitionidrequestbody.md) | :heavy_check_mark:                                                                                     | The request object to use for the request.                                                             |


### Response

**[*operations.GetDestinationDefinitionResponse](../../models/operations/getdestinationdefinitionresponse.md), error**


## GetDestinationDefinitionForWorkspace

Get a destinationDefinition that is configured for the given workspace

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
    res, err := s.DestinationDefinition.GetDestinationDefinitionForWorkspace(ctx, shared.DestinationDefinitionIDWithWorkspaceID{
        DestinationDefinitionID: "895c537c-6454-4efb-8b34-896c3ca5acfb",
        WorkspaceID: "e2fd5707-5779-4291-b7de-ac646ecb5734",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                      | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                          | :heavy_check_mark:                                                                                             | The context to use for the request.                                                                            |
| `request`                                                                                                      | [shared.DestinationDefinitionIDWithWorkspaceID](../../models/shared/destinationdefinitionidwithworkspaceid.md) | :heavy_check_mark:                                                                                             | The request object to use for the request.                                                                     |


### Response

**[*operations.GetDestinationDefinitionForWorkspaceResponse](../../models/operations/getdestinationdefinitionforworkspaceresponse.md), error**


## GrantDestinationDefinitionToWorkspace

grant a private, non-custom destinationDefinition to a given workspace

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
    res, err := s.DestinationDefinition.GrantDestinationDefinitionToWorkspace(ctx, shared.DestinationDefinitionIDWithWorkspaceID{
        DestinationDefinitionID: "09e3eb1e-5a2b-412e-b07f-116db99545fc",
        WorkspaceID: "95fa8897-0e18-49db-b30f-cb33ea055b19",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.PrivateDestinationDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                      | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                          | :heavy_check_mark:                                                                                             | The context to use for the request.                                                                            |
| `request`                                                                                                      | [shared.DestinationDefinitionIDWithWorkspaceID](../../models/shared/destinationdefinitionidwithworkspaceid.md) | :heavy_check_mark:                                                                                             | The request object to use for the request.                                                                     |


### Response

**[*operations.GrantDestinationDefinitionToWorkspaceResponse](../../models/operations/grantdestinationdefinitiontoworkspaceresponse.md), error**


## ListDestinationDefinitions

List all the destinationDefinitions the current Airbyte deployment is configured to use

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
    res, err := s.DestinationDefinition.ListDestinationDefinitions(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.ListDestinationDefinitionsResponse](../../models/operations/listdestinationdefinitionsresponse.md), error**


## ListDestinationDefinitionsForWorkspace

List all the destinationDefinitions the given workspace is configured to use

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
    res, err := s.DestinationDefinition.ListDestinationDefinitionsForWorkspace(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "7cd44e2f-52d8-42d3-913b-b6f48b656bcd",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionReadList != nil {
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

**[*operations.ListDestinationDefinitionsForWorkspaceResponse](../../models/operations/listdestinationdefinitionsforworkspaceresponse.md), error**


## ListLatestDestinationDefinitions

Guaranteed to retrieve the latest information on supported destinations.

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
    res, err := s.DestinationDefinition.ListLatestDestinationDefinitions(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.ListLatestDestinationDefinitionsResponse](../../models/operations/listlatestdestinationdefinitionsresponse.md), error**


## ListPrivateDestinationDefinitions

List all private, non-custom destinationDefinitions, and for each indicate whether the given workspace has a grant for using the definition. Used by admins to view and modify a given workspace's grants.

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
    res, err := s.DestinationDefinition.ListPrivateDestinationDefinitions(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "b35ff2e4-b275-437a-8cd9-e7319c177d52",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.PrivateDestinationDefinitionReadList != nil {
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

**[*operations.ListPrivateDestinationDefinitionsResponse](../../models/operations/listprivatedestinationdefinitionsresponse.md), error**


## RevokeDestinationDefinitionFromWorkspace

revoke a grant to a private, non-custom destinationDefinition from a given workspace

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
    res, err := s.DestinationDefinition.RevokeDestinationDefinitionFromWorkspace(ctx, shared.DestinationDefinitionIDWithWorkspaceID{
        DestinationDefinitionID: "5f77b114-eeb5-42ff-b85f-c37814d4c98e",
        WorkspaceID: "0c2bb89e-b75d-4ad6-b6c6-00503d8bb311",
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

| Parameter                                                                                                      | Type                                                                                                           | Required                                                                                                       | Description                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                                          | :heavy_check_mark:                                                                                             | The context to use for the request.                                                                            |
| `request`                                                                                                      | [shared.DestinationDefinitionIDWithWorkspaceID](../../models/shared/destinationdefinitionidwithworkspaceid.md) | :heavy_check_mark:                                                                                             | The request object to use for the request.                                                                     |


### Response

**[*operations.RevokeDestinationDefinitionFromWorkspaceResponse](../../models/operations/revokedestinationdefinitionfromworkspaceresponse.md), error**


## UpdateDestinationDefinition

Update destinationDefinition

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
    res, err := s.DestinationDefinition.UpdateDestinationDefinition(ctx, shared.DestinationDefinitionUpdate{
        DestinationDefinitionID: "80f739ae-9e05-47eb-809e-2810331f3981",
        DockerImageTag: airbytetest.String("at"),
        ResourceRequirements: &shared.ActorDefinitionResourceRequirements{
            Default: &shared.ResourceRequirements{
                CPULimit: airbytetest.String("labore"),
                CPURequest: airbytetest.String("minus"),
                MemoryLimit: airbytetest.String("esse"),
                MemoryRequest: airbytetest.String("voluptatem"),
            },
            JobSpecific: []shared.JobTypeResourceLimit{
                shared.JobTypeResourceLimit{
                    JobType: shared.JobTypeResetConnection,
                    ResourceRequirements: shared.ResourceRequirements{
                        CPULimit: airbytetest.String("ea"),
                        CPURequest: airbytetest.String("aperiam"),
                        MemoryLimit: airbytetest.String("dignissimos"),
                        MemoryRequest: airbytetest.String("repellat"),
                    },
                },
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                | Type                                                                                     | Required                                                                                 | Description                                                                              |
| ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| `ctx`                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                    | :heavy_check_mark:                                                                       | The context to use for the request.                                                      |
| `request`                                                                                | [shared.DestinationDefinitionUpdate](../../models/shared/destinationdefinitionupdate.md) | :heavy_check_mark:                                                                       | The request object to use for the request.                                               |


### Response

**[*operations.UpdateDestinationDefinitionResponse](../../models/operations/updatedestinationdefinitionresponse.md), error**

