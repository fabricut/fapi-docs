# Overview

## Current Version

The current version of this API is `v2`. The version is defined using the `Accept` header. To request version two the header would be `application/vnd.fabricut.v2`.

## Date / Time Representations

All date/time representations are on ISO 8601 format: `YYYY-MM-DDTHH:MM:SSZ`. The returned timezone is UTC.

## Authentication

All API requests require a valid JSON Web Token (JWT). To retrieve a users token send a post requests to the `/user_token` endpoint.

### HTTP Request

`POST https://fabricut-fapi.herokuapp.com/user_token`

> To retrieve a users API key, use this code:

``` shell
## Create User Token
curl -X "POST" "https://fabricut-fapi.herokuapp.com/user_token" \
     -d $'{
  "auth": {
    "email": "charles@fabricut.com",
    "password": "charles-password"
  }
}'
```

## Authorization

Fabricut uses API keys in the form of JSON Web Tokens to allow access to the API. Any API requests need to send the API key via the `Authorization` header.

``` shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: charles-json-web-token-api-key"
```

> Make sure to replace `charles-json-web-token-api-key` with your API key.

The API expects for a key to be included in a header that looks like the following:

`Authorization: charles-json-web-token-api-key`

<aside class="notice">
You must replace <code>charles-json-web-token-api-key</code> with your personal API key.
</aside>

See the [authentication](#authentication) section for how to retrieve a users API key.

## Pagination

Requests that return multiple items will be paginated to 25 items by default. You can specify further pages with the ?page parameter. For some resources, you can also set a custom page size up to 100 with the ?per_page parameter.

## Rate Limiting

You can check the returned HTTP headers of any API request to see your current rate limit status.

If you have abused the limits, you will receive a 429 error.

## Cross Origin Resouce Sharing

The API supports Cross Origin Resource Sharing (CORS) for AJAX requests from any origin.

## Meta data

In each GET request that acts upon resources, there is an extra field in the response under “meta” root element. It includes, the current requested page, next page, previous page, total pages and the total number of resources under the given params.
