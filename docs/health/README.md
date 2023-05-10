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
