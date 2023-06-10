# Workspace

## Overview

Workspace related resources.

### Available Operations

* [CreateWorkspace](#createworkspace) - Creates a workspace
* [DeleteWorkspace](#deleteworkspace) - Deletes a workspace
* [GetWorkspace](#getworkspace) - Find workspace by ID
* [GetWorkspaceByConnectionID](#getworkspacebyconnectionid) - Find workspace by connection id
* [GetWorkspaceBySlug](#getworkspacebyslug) - Find workspace by slug
* [ListWorkspaces](#listworkspaces) - List all workspaces registered in the current Airbyte deployment
* [UpdateWorkspace](#updateworkspace) - Update workspace state
* [UpdateWorkspaceFeedback](#updateworkspacefeedback) - Update workspace feedback state
* [UpdateWorkspaceName](#updateworkspacename) - Update workspace name

## CreateWorkspace

Creates a workspace

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
    res, err := s.Workspace.CreateWorkspace(ctx, shared.WorkspaceCreate{
        AnonymousDataCollection: airbytetest.Bool(false),
        DefaultGeography: shared.GeographyUs.ToPointer(),
        DisplaySetupWizard: airbytetest.Bool(false),
        Email: airbytetest.String("Eliseo_Feil@hotmail.com"),
        Name: "Becky Daugherty",
        News: airbytetest.Bool(false),
        Notifications: []shared.Notification{
            shared.Notification{
                CustomerioConfiguration: &shared.CustomerioNotificationConfiguration{},
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "temporibus",
                },
            },
            shared.Notification{
                CustomerioConfiguration: &shared.CustomerioNotificationConfiguration{},
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "quaerat",
                },
            },
            shared.Notification{
                CustomerioConfiguration: &shared.CustomerioNotificationConfiguration{},
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "molestiae",
                },
            },
            shared.Notification{
                CustomerioConfiguration: &shared.CustomerioNotificationConfiguration{},
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "laborum",
                },
            },
        },
        SecurityUpdates: airbytetest.Bool(false),
        WebhookConfigs: []shared.WebhookConfigWrite{
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("rerum"),
                Name: airbytetest.String("Mr. Megan Botsford"),
                ValidationURL: airbytetest.String("perspiciatis"),
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                        | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `ctx`                                                            | [context.Context](https://pkg.go.dev/context#Context)            | :heavy_check_mark:                                               | The context to use for the request.                              |
| `request`                                                        | [shared.WorkspaceCreate](../../models/shared/workspacecreate.md) | :heavy_check_mark:                                               | The request object to use for the request.                       |


### Response

**[*operations.CreateWorkspaceResponse](../../models/operations/createworkspaceresponse.md), error**


## DeleteWorkspace

Deletes a workspace

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
    res, err := s.Workspace.DeleteWorkspace(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "5d1e6698-fcc4-4596-a17c-297767633425",
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

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.WorkspaceIDRequestBody](../../models/shared/workspaceidrequestbody.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |


### Response

**[*operations.DeleteWorkspaceResponse](../../models/operations/deleteworkspaceresponse.md), error**


## GetWorkspace

Find workspace by ID

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
    res, err := s.Workspace.GetWorkspace(ctx, shared.WorkspaceIDRequestBody{
        WorkspaceID: "4038bfb5-971e-4981-9055-7389cedbac7f",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
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

**[*operations.GetWorkspaceResponse](../../models/operations/getworkspaceresponse.md), error**


## GetWorkspaceByConnectionID

Find workspace by connection id

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
    res, err := s.Workspace.GetWorkspaceByConnectionID(ctx, shared.ConnectionIDRequestBody{
        ConnectionID: "da39594d-66bc-42ae-8806-32b9954b6fa2",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
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

**[*operations.GetWorkspaceByConnectionIDResponse](../../models/operations/getworkspacebyconnectionidresponse.md), error**


## GetWorkspaceBySlug

Find workspace by slug

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
    res, err := s.Workspace.GetWorkspaceBySlug(ctx, shared.SlugRequestBody{
        Slug: "explicabo",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                        | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `ctx`                                                            | [context.Context](https://pkg.go.dev/context#Context)            | :heavy_check_mark:                                               | The context to use for the request.                              |
| `request`                                                        | [shared.SlugRequestBody](../../models/shared/slugrequestbody.md) | :heavy_check_mark:                                               | The request object to use for the request.                       |


### Response

**[*operations.GetWorkspaceBySlugResponse](../../models/operations/getworkspacebyslugresponse.md), error**


## ListWorkspaces

List all workspaces registered in the current Airbyte deployment

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
    res, err := s.Workspace.ListWorkspaces(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.ListWorkspacesResponse](../../models/operations/listworkspacesresponse.md), error**


## UpdateWorkspace

Update workspace state

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
    res, err := s.Workspace.UpdateWorkspace(ctx, shared.WorkspaceUpdate{
        AnonymousDataCollection: airbytetest.Bool(false),
        DefaultGeography: shared.GeographyAuto.ToPointer(),
        DisplaySetupWizard: airbytetest.Bool(false),
        Email: airbytetest.String("Colten_Johnson@yahoo.com"),
        InitialSetupComplete: airbytetest.Bool(false),
        News: airbytetest.Bool(false),
        Notifications: []shared.Notification{
            shared.Notification{
                CustomerioConfiguration: &shared.CustomerioNotificationConfiguration{},
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "ipsam",
                },
            },
        },
        SecurityUpdates: airbytetest.Bool(false),
        WebhookConfigs: []shared.WebhookConfigWrite{
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("sequi"),
                Name: airbytetest.String("Mr. Pete Bergstrom III"),
                ValidationURL: airbytetest.String("tempore"),
            },
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("necessitatibus"),
                Name: airbytetest.String("Randall McLaughlin DVM"),
                ValidationURL: airbytetest.String("quod"),
            },
        },
        WorkspaceID: "2053b749-366a-4c8e-a0f2-bf19588d40d0",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                        | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `ctx`                                                            | [context.Context](https://pkg.go.dev/context#Context)            | :heavy_check_mark:                                               | The context to use for the request.                              |
| `request`                                                        | [shared.WorkspaceUpdate](../../models/shared/workspaceupdate.md) | :heavy_check_mark:                                               | The request object to use for the request.                       |


### Response

**[*operations.UpdateWorkspaceResponse](../../models/operations/updateworkspaceresponse.md), error**


## UpdateWorkspaceFeedback

Update workspace feedback state

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
    res, err := s.Workspace.UpdateWorkspaceFeedback(ctx, shared.WorkspaceGiveFeedback{
        WorkspaceID: "3f3deba2-97be-43e9-8bc4-0df868fd5240",
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

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `ctx`                                                                        | [context.Context](https://pkg.go.dev/context#Context)                        | :heavy_check_mark:                                                           | The context to use for the request.                                          |
| `request`                                                                    | [shared.WorkspaceGiveFeedback](../../models/shared/workspacegivefeedback.md) | :heavy_check_mark:                                                           | The request object to use for the request.                                   |


### Response

**[*operations.UpdateWorkspaceFeedbackResponse](../../models/operations/updateworkspacefeedbackresponse.md), error**


## UpdateWorkspaceName

Update workspace name

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
    res, err := s.Workspace.UpdateWorkspaceName(ctx, shared.WorkspaceUpdateName{
        Name: "Leticia Renner",
        WorkspaceID: "1d492f4f-127f-4b0e-8bf1-f8217978d0ac",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [shared.WorkspaceUpdateName](../../models/shared/workspaceupdatename.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |


### Response

**[*operations.UpdateWorkspaceNameResponse](../../models/operations/updateworkspacenameresponse.md), error**

