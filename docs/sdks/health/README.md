# Health

## Overview

Healthchecks

### Available Operations

* [GetHealthCheck](#gethealthcheck) - Health Check

## GetHealthCheck

Health Check

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
    res, err := s.Health.GetHealthCheck(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.HealthCheckRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                             | Type                                                  | Required                                              | Description                                           |
| ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- | ----------------------------------------------------- |
| `ctx`                                                 | [context.Context](https://pkg.go.dev/context#Context) | :heavy_check_mark:                                    | The context to use for the request.                   |


### Response

**[*operations.GetHealthCheckResponse](../../models/operations/gethealthcheckresponse.md), error**

