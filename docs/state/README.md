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
        ConnectionID: "15ceb4d6-e1ea-4e0f-b5ae-df2acab58b99",
        ConnectionState: shared.ConnectionState{
            ConnectionID: "1c926ddb-5894-461e-b421-cbe6d9502f0e",
            GlobalState: &shared.GlobalState{
                SharedState: map[string]interface{}{
                    "error": "ratione",
                    "perferendis": "distinctio",
                    "voluptas": "sint",
                },
                StreamStates: []shared.StreamState{
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Lee Runte",
                            Namespace: airbytetest.String("esse"),
                        },
                        StreamState: map[string]interface{}{
                            "delectus": "quos",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Miss Jon Bailey I",
                            Namespace: airbytetest.String("occaecati"),
                        },
                        StreamState: map[string]interface{}{
                            "veritatis": "ex",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Ms. Tracey D'Amore",
                            Namespace: airbytetest.String("blanditiis"),
                        },
                        StreamState: map[string]interface{}{
                            "voluptates": "minus",
                            "autem": "vel",
                            "beatae": "quos",
                        },
                    },
                    shared.StreamState{
                        StreamDescriptor: shared.StreamDescriptor{
                            Name: "Latoya West",
                            Namespace: airbytetest.String("suscipit"),
                        },
                        StreamState: map[string]interface{}{
                            "unde": "debitis",
                            "quidem": "magnam",
                        },
                    },
                },
            },
            State: map[string]interface{}{
                "accusamus": "quod",
            },
            StateType: shared.ConnectionStateTypeGlobal,
            StreamState: []shared.StreamState{
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Cameron Wehner",
                        Namespace: airbytetest.String("rerum"),
                    },
                    StreamState: map[string]interface{}{
                        "nam": "ullam",
                    },
                },
                shared.StreamState{
                    StreamDescriptor: shared.StreamDescriptor{
                        Name: "Lois Ondricka",
                        Namespace: airbytetest.String("error"),
                    },
                    StreamState: map[string]interface{}{
                        "reprehenderit": "eligendi",
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
        ConnectionID: "baaf4452-c484-42c9-b2ad-32dafe81a88f",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.ConnectionState != nil {
        // handle response
    }
}
```
