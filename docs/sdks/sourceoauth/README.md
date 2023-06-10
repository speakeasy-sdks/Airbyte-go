# SourceOauth

## Overview

Source OAuth related resources to delegate access from user.

### Available Operations

* [CompleteSourceOAuth](#completesourceoauth) - Given a source def ID generate an access/refresh token etc.
* [GetSourceOAuthConsent](#getsourceoauthconsent) - Given a source connector definition ID, return the URL to the consent screen where to redirect the user to.
* [SetInstancewideSourceOauthParams](#setinstancewidesourceoauthparams) - Sets instancewide variables to be used for the oauth flow when creating this source. When set, these variables will be injected into a connector's configuration before any interaction with the connector image itself. This enables running oauth flows with consistent variables e.g: the company's Google Ads developer_token, client_id, and client_secret without the user having to know about these variables.


## CompleteSourceOAuth

Given a source def ID generate an access/refresh token etc.

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
    res, err := s.SourceOauth.CompleteSourceOAuth(ctx, shared.CompleteSourceOauthRequest{
        OAuthInputConfiguration: airbytetest.String("incidunt"),
        QueryParams: map[string]interface{}{
            "sunt": "ullam",
            "quam": "illum",
            "voluptates": "officia",
            "est": "in",
        },
        RedirectURL: airbytetest.String("illo"),
        SourceDefinitionID: "70f445ac-cf66-47aa-b9bb-ad185fe431d6",
        SourceID: airbytetest.String("bf5c838f-bb8c-420c-b67f-c4b425e99e62"),
        WorkspaceID: "34c9f7b7-9dfe-4b77-a5c3-8d4baf91e506",
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

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `ctx`                                                                                  | [context.Context](https://pkg.go.dev/context#Context)                                  | :heavy_check_mark:                                                                     | The context to use for the request.                                                    |
| `request`                                                                              | [shared.CompleteSourceOauthRequest](../../models/shared/completesourceoauthrequest.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |


### Response

**[*operations.CompleteSourceOAuthResponse](../../models/operations/completesourceoauthresponse.md), error**


## GetSourceOAuthConsent

Given a source connector definition ID, return the URL to the consent screen where to redirect the user to.

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
    res, err := s.SourceOauth.GetSourceOAuthConsent(ctx, shared.SourceOauthConsentRequest{
        OAuthInputConfiguration: airbytetest.String("eveniet"),
        RedirectURL: "delectus",
        SourceDefinitionID: "890a54b4-75f1-46f5-ad38-5a3c4ac631b9",
        SourceID: airbytetest.String("9e26ced8-f9fd-4b94-90f6-3bbf817837b0"),
        WorkspaceID: "1afdd788-6241-489e-b448-73f5033f19db",
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

| Parameter                                                                            | Type                                                                                 | Required                                                                             | Description                                                                          |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------ |
| `ctx`                                                                                | [context.Context](https://pkg.go.dev/context#Context)                                | :heavy_check_mark:                                                                   | The context to use for the request.                                                  |
| `request`                                                                            | [shared.SourceOauthConsentRequest](../../models/shared/sourceoauthconsentrequest.md) | :heavy_check_mark:                                                                   | The request object to use for the request.                                           |


### Response

**[*operations.GetSourceOAuthConsentResponse](../../models/operations/getsourceoauthconsentresponse.md), error**


## SetInstancewideSourceOauthParams

Sets instancewide variables to be used for the oauth flow when creating this source. When set, these variables will be injected into a connector's configuration before any interaction with the connector image itself. This enables running oauth flows with consistent variables e.g: the company's Google Ads developer_token, client_id, and client_secret without the user having to know about these variables.


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
    res, err := s.SourceOauth.SetInstancewideSourceOauthParams(ctx, shared.SetInstancewideSourceOauthParamsRequestBody{
        Params: map[string]interface{}{
            "quasi": "consequuntur",
            "nemo": "nobis",
            "debitis": "labore",
            "veritatis": "minima",
        },
        SourceDefinitionID: "2eab9cd7-e522-44a6-a0e1-23b7847ec59e",
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

| Parameter                                                                                                                | Type                                                                                                                     | Required                                                                                                                 | Description                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `ctx`                                                                                                                    | [context.Context](https://pkg.go.dev/context#Context)                                                                    | :heavy_check_mark:                                                                                                       | The context to use for the request.                                                                                      |
| `request`                                                                                                                | [shared.SetInstancewideSourceOauthParamsRequestBody](../../models/shared/setinstancewidesourceoauthparamsrequestbody.md) | :heavy_check_mark:                                                                                                       | The request object to use for the request.                                                                               |


### Response

**[*operations.SetInstancewideSourceOauthParamsResponse](../../models/operations/setinstancewidesourceoauthparamsresponse.md), error**

