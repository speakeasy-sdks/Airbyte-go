# Jobs

### Available Operations

* [CancelJob](#canceljob) - Cancels a job
* [GetAttemptNormalizationStatusesForJob](#getattemptnormalizationstatusesforjob) - Get normalization status to determine if we can bypass normalization phase
* [GetJobDebugInfo](#getjobdebuginfo) - Gets all information needed to debug this job
* [GetJobInfo](#getjobinfo) - Get information about a job
* [GetJobInfoLight](#getjobinfolight) - Get information about a job excluding attempt info and logs
* [GetLastReplicationJob](#getlastreplicationjob)
* [ListJobsFor](#listjobsfor) - Returns recent jobs for a connection. Jobs are returned in descending order by createdAt.

## CancelJob

Cancels a job

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
    res, err := s.Jobs.CancelJob(ctx, shared.JobIDRequestBody{
        ID: 556133,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.JobInfoRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.JobIDRequestBody](../../models/shared/jobidrequestbody.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.CancelJobResponse](../../models/operations/canceljobresponse.md), error**


## GetAttemptNormalizationStatusesForJob

Get normalization status to determine if we can bypass normalization phase

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
    res, err := s.Jobs.GetAttemptNormalizationStatusesForJob(ctx, shared.JobIDRequestBody{
        ID: 811259,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.AttemptNormalizationStatusReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.JobIDRequestBody](../../models/shared/jobidrequestbody.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.GetAttemptNormalizationStatusesForJobResponse](../../models/operations/getattemptnormalizationstatusesforjobresponse.md), error**


## GetJobDebugInfo

Gets all information needed to debug this job

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
    res, err := s.Jobs.GetJobDebugInfo(ctx, shared.JobIDRequestBody{
        ID: 318028,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.JobDebugInfoRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.JobIDRequestBody](../../models/shared/jobidrequestbody.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.GetJobDebugInfoResponse](../../models/operations/getjobdebuginforesponse.md), error**


## GetJobInfo

Get information about a job

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
    res, err := s.Jobs.GetJobInfo(ctx, shared.JobIDRequestBody{
        ID: 286453,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.JobInfoRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.JobIDRequestBody](../../models/shared/jobidrequestbody.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.GetJobInfoResponse](../../models/operations/getjobinforesponse.md), error**


## GetJobInfoLight

Get information about a job excluding attempt info and logs

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
    res, err := s.Jobs.GetJobInfoLight(ctx, shared.JobIDRequestBody{
        ID: 958068,
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.JobInfoLightRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `ctx`                                                              | [context.Context](https://pkg.go.dev/context#Context)              | :heavy_check_mark:                                                 | The context to use for the request.                                |
| `request`                                                          | [shared.JobIDRequestBody](../../models/shared/jobidrequestbody.md) | :heavy_check_mark:                                                 | The request object to use for the request.                         |


### Response

**[*operations.GetJobInfoLightResponse](../../models/operations/getjobinfolightresponse.md), error**


## GetLastReplicationJob

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
    res, err := s.Jobs.GetLastReplicationJob(ctx, shared.ConnectionIDRequestBody{
        ConnectionID: "efa9c95f-2eac-4556-9d30-7cfee81206e2",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.JobOptionalRead != nil {
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

**[*operations.GetLastReplicationJobResponse](../../models/operations/getlastreplicationjobresponse.md), error**


## ListJobsFor

Returns recent jobs for a connection. Jobs are returned in descending order by createdAt.

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
    res, err := s.Jobs.ListJobsFor(ctx, shared.JobListRequestBody{
        ConfigID: "deleniti",
        ConfigTypes: []shared.JobConfigType{
            shared.JobConfigTypeCheckConnectionDestination,
        },
        IncludingJobID: airbytetest.Int64(963913),
        Pagination: &shared.Pagination{
            PageSize: airbytetest.Int64(673653),
            RowOffset: airbytetest.Int64(303421),
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.JobReadList != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                              | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `ctx`                                                                  | [context.Context](https://pkg.go.dev/context#Context)                  | :heavy_check_mark:                                                     | The context to use for the request.                                    |
| `request`                                                              | [shared.JobListRequestBody](../../models/shared/joblistrequestbody.md) | :heavy_check_mark:                                                     | The request object to use for the request.                             |


### Response

**[*operations.ListJobsForResponse](../../models/operations/listjobsforresponse.md), error**

