# DestinationOauth

## Overview

Source OAuth related resources to delegate access from user.

### Available Operations

* [CompleteDestinationOAuth](#completedestinationoauth) - Given a destination def ID generate an access/refresh token etc.
* [GetDestinationOAuthConsent](#getdestinationoauthconsent) - Given a destination connector definition ID, return the URL to the consent screen where to redirect the user to.
* [SetInstancewideDestinationOauthParams](#setinstancewidedestinationoauthparams) - Sets instancewide variables to be used for the oauth flow when creating this destination. When set, these variables will be injected into a connector's configuration before any interaction with the connector image itself. This enables running oauth flows with consistent variables e.g: the company's Google Ads developer_token, client_id, and client_secret without the user having to know about these variables.


## CompleteDestinationOAuth

Given a destination def ID generate an access/refresh token etc.

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
    res, err := s.DestinationOauth.CompleteDestinationOAuth(ctx, shared.CompleteDestinationOAuthRequest{
        DestinationDefinitionID: "75f1400e-764a-4d73-b4ec-1b781b36a080",
        DestinationID: airbytetest.String("88d100ef-ada2-400e-b042-2eb2164cf9ab"),
        OAuthInputConfiguration: airbytetest.String("totam"),
        QueryParams: map[string]interface{}{
            "aliquid": "ea",
        },
        RedirectURL: airbytetest.String("impedit"),
        WorkspaceID: "723ffda9-e06b-4ee4-825c-1fc0e115c80b",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.CompleteOAuthResponse != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                            | [context.Context](https://pkg.go.dev/context#Context)                                            | :heavy_check_mark:                                                                               | The context to use for the request.                                                              |
| `request`                                                                                        | [shared.CompleteDestinationOAuthRequest](../../models/shared/completedestinationoauthrequest.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |


### Response

**[*operations.CompleteDestinationOAuthResponse](../../models/operations/completedestinationoauthresponse.md), error**


## GetDestinationOAuthConsent

Given a destination connector definition ID, return the URL to the consent screen where to redirect the user to.

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
    res, err := s.DestinationOauth.GetDestinationOAuthConsent(ctx, shared.DestinationOauthConsentRequest{
        DestinationDefinitionID: "ff918544-ec42-4def-8ce8-f1977773e635",
        DestinationID: airbytetest.String("62a7b408-f05e-43d4-8fda-f313a1f5fd94"),
        OAuthInputConfiguration: airbytetest.String("explicabo"),
        RedirectURL: "ipsam",
        WorkspaceID: "9c0b36f2-5ea9-444f-bb75-6c11f6c37a51",
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.OAuthConsentRead != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `request`                                                                                      | [shared.DestinationOauthConsentRequest](../../models/shared/destinationoauthconsentrequest.md) | :heavy_check_mark:                                                                             | The request object to use for the request.                                                     |


### Response

**[*operations.GetDestinationOAuthConsentResponse](../../models/operations/getdestinationoauthconsentresponse.md), error**


## SetInstancewideDestinationOauthParams

Sets instancewide variables to be used for the oauth flow when creating this destination. When set, these variables will be injected into a connector's configuration before any interaction with the connector image itself. This enables running oauth flows with consistent variables e.g: the company's Google Ads developer_token, client_id, and client_secret without the user having to know about these variables.


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
    res, err := s.DestinationOauth.SetInstancewideDestinationOauthParams(ctx, shared.SetInstancewideDestinationOauthParamsRequestBody{
        DestinationDefinitionID: "26243835-bbc0-45a2-ba45-cefc5fde10a0",
        Params: map[string]interface{}{
            "necessitatibus": "quia",
            "dicta": "vel",
            "perspiciatis": "debitis",
            "ullam": "architecto",
        },
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

| Parameter                                                                                                                          | Type                                                                                                                               | Required                                                                                                                           | Description                                                                                                                        |
| ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| `ctx`                                                                                                                              | [context.Context](https://pkg.go.dev/context#Context)                                                                              | :heavy_check_mark:                                                                                                                 | The context to use for the request.                                                                                                |
| `request`                                                                                                                          | [shared.SetInstancewideDestinationOauthParamsRequestBody](../../models/shared/setinstancewidedestinationoauthparamsrequestbody.md) | :heavy_check_mark:                                                                                                                 | The request object to use for the request.                                                                                         |


### Response

**[*operations.SetInstancewideDestinationOauthParamsResponse](../../models/operations/setinstancewidedestinationoauthparamsresponse.md), error**

