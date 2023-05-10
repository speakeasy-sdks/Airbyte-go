# Openapi

### Available Operations

* [GetOpenAPISpec](#getopenapispec) - Returns the openapi specification

## GetOpenAPISpec

Returns the openapi specification

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
    res, err := s.Openapi.GetOpenAPISpec(ctx)
    if err != nil {
        log.Fatal(err)
    }

    if res.GetOpenAPISpec200TextPlainBinaryString != nil {
        // handle response
    }
}
```
