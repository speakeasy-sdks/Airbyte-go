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
        LogType: shared.LogTypeScheduler,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.GetLogs200TextPlainBinaryString != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                        | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `ctx`                                                            | [context.Context](https://pkg.go.dev/context#Context)            | :heavy_check_mark:                                               | The context to use for the request.                              |
| `request`                                                        | [shared.LogsRequestBody](../../models/shared/logsrequestbody.md) | :heavy_check_mark:                                               | The request object to use for the request.                       |


### Response

**[*operations.GetLogsResponse](../../models/operations/getlogsresponse.md), error**

