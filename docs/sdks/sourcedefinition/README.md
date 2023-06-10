# SourceDefinition

## Overview

SourceDefinition related resources.

### Available Operations

* [CreateCustomSourceDefinition](#createcustomsourcedefinition) - Creates a custom sourceDefinition for the given workspace
* [DeleteSourceDefinition](#deletesourcedefinition) - Delete a source definition
* [GetSourceDefinition](#getsourcedefinition) - Get source
* [GetSourceDefinitionForWorkspace](#getsourcedefinitionforworkspace) - Get a sourceDefinition that is configured for the given workspace
* [GrantSourceDefinitionToWorkspace](#grantsourcedefinitiontoworkspace) - grant a private, non-custom sourceDefinition to a given workspace
* [ListLatestSourceDefinitions](#listlatestsourcedefinitions) - List the latest sourceDefinitions Airbyte supports
* [ListPrivateSourceDefinitions](#listprivatesourcedefinitions) - List all private, non-custom sourceDefinitions, and for each indicate whether the given workspace has a grant for using the definition. Used by admins to view and modify a given workspace's grants.
* [ListSourceDefinitions](#listsourcedefinitions) - List all the sourceDefinitions the current Airbyte deployment is configured to use
* [ListSourceDefinitionsForWorkspace](#listsourcedefinitionsforworkspace) - List all the sourceDefinitions the given workspace is configured to use
* [RevokeSourceDefinitionFromWorkspace](#revokesourcedefinitionfromworkspace) - revoke a grant to a private, non-custom sourceDefinition from a given workspace
* [UpdateSourceDefinition](#updatesourcedefinition) - Update a sourceDefinition

## CreateCustomSourceDefinition

Creates a custom sourceDefinition for the given workspace

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
    res, err := s.SourceDefinition.CreateCustomSourceDefinition(ctx, shared.CustomSourceDefinitionCreate{
        SourceDefinition: shared.SourceDefinitionCreate{
            DockerImageTag: "vero",
            DockerRepository: "eos",
            DocumentationURL: "http://tattered-pilgrimage.com",
            Icon: airbytetest.String("commodi"),
            Name: "Sylvester Cormier",
            ResourceRequirements: &shared.ActorDefinitionResourceRequirements{
                Default: &shared.ResourceRequirements{
                    CPULimit: airbytetest.String("iusto"),
                    CPURequest: airbytetest.String("ab"),
                    MemoryLimit: airbytetest.String("deserunt"),
                    MemoryRequest: airbytetest.String("sed"),
                },
                JobSpecific: []shared.JobTypeResourceLimit{
                    shared.JobTypeResourceLimit{
                        JobType: shared.JobTypeResetConnection,
                        ResourceRequirements: shared.ResourceRequirements{
                            CPULimit: airbytetest.String("placeat"),
                            CPURequest: airbytetest.String("ullam"),
                            MemoryLimit: airbytetest.String("molestiae"),
                            MemoryRequest: airbytetest.String("itaque"),
                        },
                    },
                    shared.JobTypeResourceLimit{
                        JobType: shared.JobTypeSync,
                        ResourceRequirements: shared.ResourceRequirements{
                            CPULimit: airbytetest.String("nemo"),
                            CPURequest: airbytetest.String("non"),
                            MemoryLimit: airbytetest.String("recusandae"),
                            MemoryRequest: airbytetest.String("omnis"),
                        },
                    },
                    shared.JobTypeResourceLimit{
                        JobType: shared.JobTypeGetSpec,
                        ResourceRequirements: shared.ResourceRequirements{
                            CPULimit: airbytetest.String("aliquam"),
                            CPURequest: airbytetest.String("dolor"),
                            MemoryLimit: airbytetest.String("occaecati"),
                            MemoryRequest: airbytetest.String("quibusdam"),
                        },
                    },
                },
            },
        },
        WorkspaceID: "22246569-4624-4070-84f7-ab37cef02225",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `ctx`                                                                                      | [context.Context](https://pkg.go.dev/context#Context)                                      | :heavy_check_mark:                                                                         | The context to use for the request.                                                        |
| `request`                                                                                  | [shared.CustomSourceDefinitionCreate](../../models/shared/customsourcedefinitioncreate.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |


### Response

**[*operations.CreateCustomSourceDefinitionResponse](../../models/operations/createcustomsourcedefinitionresponse.md), error**


## DeleteSourceDefinition

Delete a source definition

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
    res, err := s.SourceDefinition.DeleteSourceDefinition(ctx, shared.SourceDefinitionIDRequestBody{
        SourceDefinitionID: "194db554-10ad-4c66-9af9-0a26c7cdc981",
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

| Parameter                                                                                    | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `ctx`                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                        | :heavy_check_mark:                                                                           | The context to use for the request.                                                          |
| `request`                                                                                    | [shared.SourceDefinitionIDRequestBody](../../models/shared/sourcedefinitionidrequestbody.md) | :heavy_check_mark:                                                                           | The request object to use for the request.                                                   |


### Response

**[*operations.DeleteSourceDefinitionResponse](../../models/operations/deletesourcedefinitionresponse.md), error**


## GetSourceDefinition

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
    res, err := s.SourceDefinition.GetSourceDefinition(ctx, shared.SourceDefinitionIDRequestBody{
        SourceDefinitionID: "f068981d-6bb3-43cf-aa34-8c31bf407ee4",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                    | Type                                                                                         | Required                                                                                     | Description                                                                                  |
| -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| `ctx`                                                                                        | [context.Context](https://pkg.go.dev/context#Context)                                        | :heavy_check_mark:                                                                           | The context to use for the request.                                                          |
| `request`                                                                                    | [shared.SourceDefinitionIDRequestBody](../../models/shared/sourcedefinitionidrequestbody.md) | :heavy_check_mark:                                                                           | The request object to use for the request.                                                   |


### Response

**[*operations.GetSourceDefinitionResponse](../../models/operations/getsourcedefinitionresponse.md), error**


## GetSourceDefinitionForWorkspace

Get a sourceDefinition that is configured for the given workspace

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
    res, err := s.SourceDefinition.GetSourceDefinitionForWorkspace(ctx, shared.SourceDefinitionIDWithWorkspaceID{
        SourceDefinitionID: "fcf0c42b-78f1-4562-a398-a0dc766324cc",
        WorkspaceID: "b06c8ca1-2d02-4529-a70b-8d5722dd895b",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                | :heavy_check_mark:                                                                                   | The context to use for the request.                                                                  |
| `request`                                                                                            | [shared.SourceDefinitionIDWithWorkspaceID](../../models/shared/sourcedefinitionidwithworkspaceid.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |


### Response

**[*operations.GetSourceDefinitionForWorkspaceResponse](../../models/operations/getsourcedefinitionforworkspaceresponse.md), error**


## GrantSourceDefinitionToWorkspace

grant a private, non-custom sourceDefinition to a given workspace

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
    res, err := s.SourceDefinition.GrantSourceDefinitionToWorkspace(ctx, shared.SourceDefinitionIDWithWorkspaceID{
        SourceDefinitionID: "8bcf24db-9596-4933-92f7-4533994d78de",
        WorkspaceID: "3b6e9389-f5ab-4b7f-a625-50a28382ac48",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.PrivateSourceDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                | :heavy_check_mark:                                                                                   | The context to use for the request.                                                                  |
| `request`                                                                                            | [shared.SourceDefinitionIDWithWorkspaceID](../../models/shared/sourcedefinitionidwithworkspaceid.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |


### Response

**[*operations.GrantSourceDefinitionToWorkspaceResponse](../../models/operations/grantsourcedefinitiontoworkspaceresponse.md), error**


## ListLatestSourceDefinitions

Guaranteed to retrieve the latest information on supported sources.

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
    res, err := s.SourceDefinition.ListLatestSourceDefinitions(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.ListLatestSourceDefinitionsResponse](../../models/operations/listlatestsourcedefinitionsresponse.md), error**


## ListPrivateSourceDefinitions

List all private, non-custom sourceDefinitions, and for each indicate whether the given workspace has a grant for using the definition. Used by admins to view and modify a given workspace's grants.

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
    res, err := s.SourceDefinition.ListPrivateSourceDefinitions(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "3afd2315-bba6-4501-a4e0-6f5bf6ae591b",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.PrivateSourceDefinitionReadList != nil {
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

**[*operations.ListPrivateSourceDefinitionsResponse](../../models/operations/listprivatesourcedefinitionsresponse.md), error**


## ListSourceDefinitions

List all the sourceDefinitions the current Airbyte deployment is configured to use

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
    res, err := s.SourceDefinition.ListSourceDefinitions(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.ListSourceDefinitionsResponse](../../models/operations/listsourcedefinitionsresponse.md), error**


## ListSourceDefinitionsForWorkspace

List all the sourceDefinitions the given workspace is configured to use

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
    res, err := s.SourceDefinition.ListSourceDefinitionsForWorkspace(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "c8bdef36-12b6-43c2-85fd-a840774a68a9",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionReadList != nil {
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

**[*operations.ListSourceDefinitionsForWorkspaceResponse](../../models/operations/listsourcedefinitionsforworkspaceresponse.md), error**


## RevokeSourceDefinitionFromWorkspace

revoke a grant to a private, non-custom sourceDefinition from a given workspace

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
    res, err := s.SourceDefinition.RevokeSourceDefinitionFromWorkspace(ctx, shared.SourceDefinitionIDWithWorkspaceID{
        SourceDefinitionID: "a35d086b-6f66-4fef-820e-9f443b4257b9",
        WorkspaceID: "92c8dbda-6a61-4efa-a198-258fd0a9eba4",
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

| Parameter                                                                                            | Type                                                                                                 | Required                                                                                             | Description                                                                                          |
| ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                                | :heavy_check_mark:                                                                                   | The context to use for the request.                                                                  |
| `request`                                                                                            | [shared.SourceDefinitionIDWithWorkspaceID](../../models/shared/sourcedefinitionidwithworkspaceid.md) | :heavy_check_mark:                                                                                   | The request object to use for the request.                                                           |


### Response

**[*operations.RevokeSourceDefinitionFromWorkspaceResponse](../../models/operations/revokesourcedefinitionfromworkspaceresponse.md), error**


## UpdateSourceDefinition

Update a sourceDefinition

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
    res, err := s.SourceDefinition.UpdateSourceDefinition(ctx, shared.SourceDefinitionUpdate{
        DockerImageTag: "voluptate",
        ResourceRequirements: &shared.ActorDefinitionResourceRequirements{
            Default: &shared.ResourceRequirements{
                CPULimit: airbytetest.String("voluptatibus"),
                CPURequest: airbytetest.String("quam"),
                MemoryLimit: airbytetest.String("nulla"),
                MemoryRequest: airbytetest.String("dolorem"),
            },
            JobSpecific: []shared.JobTypeResourceLimit{
                shared.JobTypeResourceLimit{
                    JobType: shared.JobTypeReplicate,
                    ResourceRequirements: shared.ResourceRequirements{
                        CPULimit: airbytetest.String("perferendis"),
                        CPURequest: airbytetest.String("quaerat"),
                        MemoryLimit: airbytetest.String("excepturi"),
                        MemoryRequest: airbytetest.String("aliquid"),
                    },
                },
                shared.JobTypeResourceLimit{
                    JobType: shared.JobTypeDiscoverSchema,
                    ResourceRequirements: shared.ResourceRequirements{
                        CPULimit: airbytetest.String("voluptatem"),
                        CPURequest: airbytetest.String("illum"),
                        MemoryLimit: airbytetest.String("laboriosam"),
                        MemoryRequest: airbytetest.String("culpa"),
                    },
                },
                shared.JobTypeResourceLimit{
                    JobType: shared.JobTypeGetSpec,
                    ResourceRequirements: shared.ResourceRequirements{
                        CPULimit: airbytetest.String("atque"),
                        CPURequest: airbytetest.String("ratione"),
                        MemoryLimit: airbytetest.String("vitae"),
                        MemoryRequest: airbytetest.String("quisquam"),
                    },
                },
                shared.JobTypeResourceLimit{
                    JobType: shared.JobTypeSync,
                    ResourceRequirements: shared.ResourceRequirements{
                        CPULimit: airbytetest.String("nihil"),
                        CPURequest: airbytetest.String("culpa"),
                        MemoryLimit: airbytetest.String("temporibus"),
                        MemoryRequest: airbytetest.String("a"),
                    },
                },
            },
        },
        SourceDefinitionID: "596fdf1a-d837-4ae8-8c1c-19c95ba99867",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.SourceDefinitionUpdate](../../models/shared/sourcedefinitionupdate.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |


### Response

**[*operations.UpdateSourceDefinitionResponse](../../models/operations/updatesourcedefinitionresponse.md), error**

