# State

## Overview

Interactions with state related resources.

### Available Operations

* [CreateOrUpdateState](#createorupdatestate) - Create or update the state for a connection.
* [GetState](#getstate) - Fetch the current state for a connection.

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
    res, err := s.State.CreateOrUpdateState(ctx, shared.ConnectionStateCreateOrUpdate{
        ConnectionID: "1f67f3c4-cce4-4b6d-b696-ff3c57475013",
        ConnectionState: shared.ConnectionState{
            ConnectionID: "57e44f51-f8b0-484c-b197-e193a245467f",
            GlobalState: &shared.GlobalState{
                SharedState: &shared.StateBlob{},
                StreamStates: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Naomi Kozey",
                            Namespace: airbytetest.String("fugit"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Vernon Rohan",
                            Namespace: airbytetest.String("perspiciatis"),
                        },
                        StreamState: &shared.StateBlob{},
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Lois Dibbert",
                            Namespace: airbytetest.String("saepe"),
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
                        Name: "Nicolas Legros",
                        Namespace: airbytetest.String("corporis"),
                    },
                    StreamState: &shared.StateBlob{},
                },
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Richard Bartell",
                        Namespace: airbytetest.String("odio"),
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


## GetState

Fetch the current state for a connection.

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
    res, err := s.State.GetState(ctx, shared.ConnectionIDRequestBody{
        ConnectionID: "9ef20387-3205-490c-8c10-96400313b3e5",
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

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `ctx`                                                                            | [context.Context](https://pkg.go.dev/context#Context)                            | :heavy_check_mark:                                                               | The context to use for the request.                                              |
| `request`                                                                        | [shared.ConnectionIDRequestBody](../../models/shared/connectionidrequestbody.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |


### Response

**[*operations.GetStateResponse](../../models/operations/getstateresponse.md), error**

