# SourceDefinitionSpecification

## Overview

SourceDefinition specification related resources.

### Available Operations

* [GetSourceDefinitionSpecification](#getsourcedefinitionspecification) - Get specification for a SourceDefinition.

## GetSourceDefinitionSpecification

Get specification for a SourceDefinition.

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
    res, err := s.SourceDefinitionSpecification.GetSourceDefinitionSpecification(ctx, shared.SourceDefinitionIDWithWorkspaceID{
        SourceDefinitionID: "8fa3f696-991a-4f38-8ce0-3614448c7977",
        WorkspaceID: "a0ef2f53-6028-4efe-af93-4152ed7e253f",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.SourceDefinitionSpecificationRead != nil {
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

**[*operations.GetSourceDefinitionSpecificationResponse](../../models/operations/getsourcedefinitionspecificationresponse.md), error**

