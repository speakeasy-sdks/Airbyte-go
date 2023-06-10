# Operation

### Available Operations

* [CheckOperation](#checkoperation) - Check if an operation to be created is valid
* [CreateOperation](#createoperation) - Create an operation to be applied as part of a connection pipeline
* [DeleteOperation](#deleteoperation) - Delete an operation
* [GetOperation](#getoperation) - Returns an operation
* [ListOperationsForConnection](#listoperationsforconnection) - Returns all operations for a connection.
* [UpdateOperation](#updateoperation) - Update an operation

## CheckOperation

Check if an operation to be created is valid

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
    res, err := s.Operation.CheckOperation(ctx, shared.OperatorConfiguration{
        Dbt: &shared.OperatorDbt{
            DbtArguments: airbytetest.String("impedit"),
            DockerImage: airbytetest.String("eius"),
            GitRepoBranch: airbytetest.String("voluptatum"),
            GitRepoURL: "ipsa",
        },
        Normalization: &shared.OperatorNormalization{
            Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
        },
        OperatorType: shared.OperatorTypeWebhook,
        Webhook: &shared.OperatorWebhook{
            DbtCloud: &shared.OperatorWebhookDbtCloud{
                AccountID: 209860,
                JobID: 999854,
            },
            ExecutionBody: airbytetest.String("aspernatur"),
            ExecutionURL: airbytetest.String("inventore"),
            WebhookConfigID: airbytetest.String("32af0310-2d51-44f4-8c6f-18bf9621a6a4"),
            WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.CheckOperationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `ctx`                                                                        | [context.Context](https://pkg.go.dev/context#Context)                        | :heavy_check_mark:                                                           | The context to use for the request.                                          |
| `request`                                                                    | [shared.OperatorConfiguration](../../models/shared/operatorconfiguration.md) | :heavy_check_mark:                                                           | The request object to use for the request.                                   |


### Response

**[*operations.CheckOperationResponse](../../models/operations/checkoperationresponse.md), error**


## CreateOperation

Create an operation to be applied as part of a connection pipeline

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
    res, err := s.Operation.CreateOperation(ctx, shared.OperationCreate{
        Name: "Julio Koch",
        OperatorConfiguration: shared.OperatorConfiguration{
            Dbt: &shared.OperatorDbt{
                DbtArguments: airbytetest.String("esse"),
                DockerImage: airbytetest.String("eveniet"),
                GitRepoBranch: airbytetest.String("earum"),
                GitRepoURL: "velit",
            },
            Normalization: &shared.OperatorNormalization{
                Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
            },
            OperatorType: shared.OperatorTypeWebhook,
            Webhook: &shared.OperatorWebhook{
                DbtCloud: &shared.OperatorWebhookDbtCloud{
                    AccountID: 263346,
                    JobID: 701978,
                },
                ExecutionBody: airbytetest.String("itaque"),
                ExecutionURL: airbytetest.String("dignissimos"),
                WebhookConfigID: airbytetest.String("52c65b34-418e-43bb-91c8-d975e0e8419d"),
                WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
            },
        },
        WorkspaceID: "8f84f144-f3e0-47ed-8c4a-a5f3cabd905a",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.OperationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                        | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `ctx`                                                            | [context.Context](https://pkg.go.dev/context#Context)            | :heavy_check_mark:                                               | The context to use for the request.                              |
| `request`                                                        | [shared.OperationCreate](../../models/shared/operationcreate.md) | :heavy_check_mark:                                               | The request object to use for the request.                       |


### Response

**[*operations.CreateOperationResponse](../../models/operations/createoperationresponse.md), error**


## DeleteOperation

Delete an operation

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
    res, err := s.Operation.DeleteOperation(ctx, shared.OperationIDRequestBody{
        OperationID: "972e0567-2822-47b2-9309-470bf7a4fa87",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.StatusCode == http.StatusOK {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.OperationIDRequestBody](../../models/shared/operationidrequestbody.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |


### Response

**[*operations.DeleteOperationResponse](../../models/operations/deleteoperationresponse.md), error**


## GetOperation

Returns an operation

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
    res, err := s.Operation.GetOperation(ctx, shared.OperationIDRequestBody{
        OperationID: "cf535a6f-ae54-4ebf-a0c3-21f023b75d23",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.OperationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `ctx`                                                                          | [context.Context](https://pkg.go.dev/context#Context)                          | :heavy_check_mark:                                                             | The context to use for the request.                                            |
| `request`                                                                      | [shared.OperationIDRequestBody](../../models/shared/operationidrequestbody.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |


### Response

**[*operations.GetOperationResponse](../../models/operations/getoperationresponse.md), error**


## ListOperationsForConnection

List operations for connection.

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
    res, err := s.Operation.ListOperationsForConnection(ctx, shared.ConnectionIDRequestBody{
        ConnectionID: "67fe1a0c-c8df-479f-8a39-6d90c364b7c1",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.OperationReadList != nil {
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

**[*operations.ListOperationsForConnectionResponse](../../models/operations/listoperationsforconnectionresponse.md), error**


## UpdateOperation

Update an operation

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
    res, err := s.Operation.UpdateOperation(ctx, shared.OperationUpdate{
        Name: "Betsy Wuckert",
        OperationID: "ce188b1c-4ee2-4c8c-ace6-11feeb1c7cbd",
        OperatorConfiguration: shared.OperatorConfiguration{
            Dbt: &shared.OperatorDbt{
                DbtArguments: airbytetest.String("cum"),
                DockerImage: airbytetest.String("suscipit"),
                GitRepoBranch: airbytetest.String("saepe"),
                GitRepoURL: "earum",
            },
            Normalization: &shared.OperatorNormalization{
                Option: shared.OperatorNormalizationOptionBasic.ToPointer(),
            },
            OperatorType: shared.OperatorTypeWebhook,
            Webhook: &shared.OperatorWebhook{
                DbtCloud: &shared.OperatorWebhookDbtCloud{
                    AccountID: 469588,
                    JobID: 310930,
                },
                ExecutionBody: airbytetest.String("ipsum"),
                ExecutionURL: airbytetest.String("ducimus"),
                WebhookConfigID: airbytetest.String("8ba25317-747d-4c91-9ad2-caf5dd6723dc"),
                WebhookType: shared.OperatorWebhookWebhookTypeDbtCloud.ToPointer(),
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.OperationRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                        | Type                                                             | Required                                                         | Description                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------------------- |
| `ctx`                                                            | [context.Context](https://pkg.go.dev/context#Context)            | :heavy_check_mark:                                               | The context to use for the request.                              |
| `request`                                                        | [shared.OperationUpdate](../../models/shared/operationupdate.md) | :heavy_check_mark:                                               | The request object to use for the request.                       |


### Response

**[*operations.UpdateOperationResponse](../../models/operations/updateoperationresponse.md), error**

