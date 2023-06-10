# DestinationDefinitionSpecification

## Overview

DestinationDefinitionSpecification related resources.

### Available Operations

* [GetDestinationDefinitionSpecification](#getdestinationdefinitionspecification) - Get specification for a destinationDefinition

## GetDestinationDefinitionSpecification

Get specification for a destinationDefinition

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
    res, err := s.DestinationDefinitionSpecification.GetDestinationDefinitionSpecification(ctx, shared.DestinationDefinitionIDWithWorkspaceID{
        DestinationDefinitionID: "3c93c73b-9da3-4f2c-ada7-e23f2257411f",
        WorkspaceID: "af4b7544-e472-4e80-a857-a5b40463a7d5",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.DestinationDefinitionSpecificationRead != nil {
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

**[*operations.GetDestinationDefinitionSpecificationResponse](../../models/operations/getdestinationdefinitionspecificationresponse.md), error**

