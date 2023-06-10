# Notifications

### Available Operations

* [TryNotificationConfig](#trynotificationconfig) - Try sending a notifications

## TryNotificationConfig

Try sending a notifications

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
    res, err := s.Notifications.TryNotificationConfig(ctx, shared.Notification{
        CustomerioConfiguration: &shared.CustomerioNotificationConfiguration{},
        NotificationType: shared.NotificationTypeSlack,
        SendOnFailure: false,
        SendOnSuccess: false,
        SlackConfiguration: &shared.SlackNotificationConfiguration{
            Webhook: "sunt",
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.NotificationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                  | Type                                                       | Required                                                   | Description                                                |
| ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- | ---------------------------------------------------------- |
| `ctx`                                                      | [context.Context](https://pkg.go.dev/context#Context)      | :heavy_check_mark:                                         | The context to use for the request.                        |
| `request`                                                  | [shared.Notification](../../models/shared/notification.md) | :heavy_check_mark:                                         | The request object to use for the request.                 |


### Response

**[*operations.TryNotificationConfigResponse](../../models/operations/trynotificationconfigresponse.md), error**

