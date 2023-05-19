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
        DefaultGeography: shared.GeographyAuto.ToPointer(),
        DisplaySetupWizard: airbytetest.Bool(false),
        Email: airbytetest.String("Franco30@yahoo.com"),
        Name: "Luz Hudson",
        News: airbytetest.Bool(false),
        Notifications: []shared.Notification{
            shared.Notification{
                CustomerioConfiguration: map[string]interface{}{
                    "voluptatibus": "facilis",
                    "doloremque": "officiis",
                    "nisi": "reprehenderit",
                },
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "alias",
                },
            },
            shared.Notification{
                CustomerioConfiguration: map[string]interface{}{
                    "ut": "hic",
                    "facere": "tenetur",
                    "saepe": "assumenda",
                },
                NotificationType: shared.NotificationTypeSlack,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "exercitationem",
                },
            },
            shared.Notification{
                CustomerioConfiguration: map[string]interface{}{
                    "sit": "recusandae",
                    "a": "exercitationem",
                },
                NotificationType: shared.NotificationTypeSlack,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "mollitia",
                },
            },
        },
        SecurityUpdates: airbytetest.Bool(false),
        WebhookConfigs: []shared.WebhookConfigWrite{
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("ut"),
                Name: airbytetest.String("Ryan Prosacco"),
                ValidationURL: airbytetest.String("recusandae"),
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
        WorkspaceID: "99731adc-05d8-45ae-adfb-70fb3874290d",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.StatusCode == http.StatusOK {
        // handle response
    }
}
```

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
        WorkspaceID: "336561ec-a16e-4f89-851b-d76eeeb518c4",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

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
        ConnectionID: "da1fad35-512f-406d-8e5b-72f0f548568a",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

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
        Slug: "consequatur",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

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
        Email: airbytetest.String("Effie2@gmail.com"),
        InitialSetupComplete: airbytetest.Bool(false),
        News: airbytetest.Bool(false),
        Notifications: []shared.Notification{
            shared.Notification{
                CustomerioConfiguration: map[string]interface{}{
                    "quibusdam": "autem",
                },
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "tempore",
                },
            },
            shared.Notification{
                CustomerioConfiguration: map[string]interface{}{
                    "modi": "ratione",
                    "aliquam": "ea",
                    "aliquam": "corporis",
                },
                NotificationType: shared.NotificationTypeCustomerio,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "ipsa",
                },
            },
            shared.Notification{
                CustomerioConfiguration: map[string]interface{}{
                    "aut": "molestias",
                },
                NotificationType: shared.NotificationTypeSlack,
                SendOnFailure: false,
                SendOnSuccess: false,
                SlackConfiguration: &shared.SlackNotificationConfiguration{
                    Webhook: "repellat",
                },
            },
        },
        SecurityUpdates: airbytetest.Bool(false),
        WebhookConfigs: []shared.WebhookConfigWrite{
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("libero"),
                Name: airbytetest.String("Alvin Runolfsdottir"),
                ValidationURL: airbytetest.String("a"),
            },
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("tenetur"),
                Name: airbytetest.String("Mr. Bernadette Quigley"),
                ValidationURL: airbytetest.String("debitis"),
            },
            shared.WebhookConfigWrite{
                AuthToken: airbytetest.String("enim"),
                Name: airbytetest.String("Eloise Hintz"),
                ValidationURL: airbytetest.String("animi"),
            },
        },
        WorkspaceID: "45ac82b8-5f8b-4c2c-aba8-da4127dd597f",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```

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
        WorkspaceID: "f4711aa1-bc74-4b86-8ecc-74f77b4848bd",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.StatusCode == http.StatusOK {
        // handle response
    }
}
```

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
        Name: "Angie Johnston I",
        WorkspaceID: "41d2c3b8-0809-4437-be06-0459bebbad02",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.WorkspaceRead != nil {
        // handle response
    }
}
```
