# Logs

### Available Operations

* [GetLogs](#getlogs) - Get logs

## GetLogs

Get logs

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
    res, err := s.Logs.GetLogs(ctx, shared.LogsRequestBody{
        LogType: shared.LogTypeServer,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.GetLogs200TextPlainBinaryString != nil {
        // handle response
    }
}
```
