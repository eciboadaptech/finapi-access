# OpenAPI\Client\AuthorizationApi

All URIs are relative to https://sandbox.finapi.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getToken()**](AuthorizationApi.md#getToken) | **POST** /api/v2/oauth/token | Get tokens |
| [**revokeToken()**](AuthorizationApi.md#revokeToken) | **POST** /api/v2/oauth/revoke | Revoke a token |


## `getToken()`

```php
getToken($grant_type, $client_id, $client_secret, $x_request_id, $refresh_token, $username, $password): \OpenAPI\Client\Model\AccessToken
```

Get tokens

finAPI implements the OAuth 2.0 Standard for authorizing applications and users within applications. OAuth uses the terminology of clients and users. A client represents an application that calls finAPI services. A service call might be in the context of a user of the client (e.g.: getting a user's bank connections), or outside any user context (e.g.: editing your client's configuration, or creating a new user for your client). In any case, every service call must be authorized by an access_token. This service can be used to get such an access_token, for either one of the client's users, or for the client itself. Also, this service can be used to refresh the access_token of a user that has previously requested an access_token.<br/><br/>To get a token, you must always pass a valid client identifier and client secret (=client credentials). You can get free client credentials for the sandbox <a href='https://www.finapi.io/jetzt-testen/' target='_blank'>here</a>. Alternatively, you can also contact us at <a href='mailto:support@finapi.io'>support@finapi.io</a>.<br/><br/>The authorization process is similar for both a user within a client, and for the client itself: <br/>&bull; To authorize a client (i.e. application), use <code>grant_type=client_credentials</code><br/>&bull; To authorize a user, use <code>grant_type=password</code><p><b>NOTE: The Content-Type of the request must be set to 'application/x-www-form-urlencoded'</b></p><br/>If the given parameters are valid, the service will respond with the authorization data. <br/>Here is an example of a response when authorizing a user: <br/><pre>{    \"access_token\": \"yvMbx_TgwdYE0hgOVb8N4ZOvxOukqfjzYOGRZcJiCjQuRGkVIBfjjV3YG4zKTGiY2aPn2cQTGaQOT8uo5uo7_QOXts1s5UBSVuRHc6a8X30RrGBTyqV9h26SUHcZPNbZ\",    \"token_type\": \"bearer\",    \"refresh_token\": \"0b9KjiBVlZLz7a4HshSAIcFuscStiXT1VzT5mgNYwCQ_dWctTDsaIjedAhD1LpsOFJ7x6K8Emf8M3VOQkwNFR9FHijALYSQw2UeRwAC2MvrOKwfF1dHmOq5VEVYEaGf6\",    \"expires_in\": 3600,    \"scope\": \"all\" }</pre><br/><p>Use the returned access_token for other service calls by sending it in a 'Authorization' header, with the word 'Bearer' in front of the token. Like this:</p><pre>Authorization: Bearer yvMbx_TgwdYE0hgOVb8N4ZOvxOukqfjzYOGRZcJiCjQuRGkVIBfjjV3YG4zKTGiY2aPn2cQTGaQOT8uo5uo7_QOXts1s5UBSVuRHc6a8X30RrGBTyqV9h26SUHcZPNbZ</pre><p>By default, the access tokens have an expiration time of one hour (however, you can change this via the service PATCH /clientConfiguration). If a token has expired, then using the token for a service call will result in a HTTP code 401. To restore access you can simply get a new token (as it is described above) or use <code>grant_type=refresh_token</code> (which works for user-related tokens only). In the latter case you just have to pass the previously received <code>refresh_token</code> for the user.</p><p>If explicit user verification is required (the 'isUserAutoVerificationEnabled' flag in the client configuration is set to false, see Client Configuration) and the user that you want to authorize is not yet verified by the client (see Verify a User), then the service will respond with HTTP code 403. If the user is locked (see 'maxUserLoginAttempts' in the Client Configuration), the service will respond with HTTP code 423.</p><p>If the current role has no privileges to call a certain service (e.g. if a user tries to create a new user, or if a client tries to access user data outside of any user context), then the request will fail with the HTTP code 403.</p><p>You should use this service only when you actually need a new token. As long as a token exists and has not expired, the service will always return the same token for the same credentials. Calling this service repeatedly with the same credentials contradicts the idea behind the tokens in OAuth, and will have a negative impact on the performance of your application. So instead of retrieving the same tokens over and over with this service, you should cache the tokens and re-use them as long as they have not expired - or at least as long as you're using the same tokens repeatedly, e.g. for the time of an active user session in your application.</p>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new OpenAPI\Client\Api\AuthorizationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$grant_type = 'grant_type_example'; // string | Determines the required type of authorization:password - authorize a user; client_credentials - authorize a client;refresh_token - refresh a user's access_token.
$client_id = 'client_id_example'; // string | Client identifier
$client_secret = 'client_secret_example'; // string | Client secret
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.
$refresh_token = 'refresh_token_example'; // string | Refresh token. Required for grant_type=refresh_token only.
$username = 'username_example'; // string | User identifier. Required for grant_type=password only.
$password = 'password_example'; // string | User password. Required for grant_type=password only.

try {
    $result = $apiInstance->getToken($grant_type, $client_id, $client_secret, $x_request_id, $refresh_token, $username, $password);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AuthorizationApi->getToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **grant_type** | **string**| Determines the required type of authorization:password - authorize a user; client_credentials - authorize a client;refresh_token - refresh a user&#39;s access_token. | |
| **client_id** | **string**| Client identifier | |
| **client_secret** | **string**| Client secret | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |
| **refresh_token** | **string**| Refresh token. Required for grant_type&#x3D;refresh_token only. | [optional] |
| **username** | **string**| User identifier. Required for grant_type&#x3D;password only. | [optional] |
| **password** | **string**| User password. Required for grant_type&#x3D;password only. | [optional] |

### Return type

[**\OpenAPI\Client\Model\AccessToken**](../Model/AccessToken.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `revokeToken()`

```php
revokeToken($token, $x_request_id, $token_type_hint)
```

Revoke a token

An additional endpoint for the OAuth 2.0 Standard, which allows clients to notify finAPI that a previously obtained refresh_token or access_token is no longer required. A successful request will invalidate the given token. The revocation of a particular token may also cause the revocation of related tokens and the underlying authorization grant. For token_type_hint=access_token finAPI will invalidate only the given access_token. For token_type_hint=refresh_token, finAPI will invalidate the refresh token and all access tokens based on the same authorization grant. If the token_type_hint is not defined, finAPI will revoke all access and refresh tokens (if applicable) that are based on the same authorization grant.<br/><br/>Note that the service responds with HTTP status code 200 both if the token has been revoked successfully, and if the client submitted an invalid token.<br/><br/>Note also that the client's access_token is required to authenticate the revocation.<br/><br/>Here is an example of how to revoke a user's refresh_token (and therefore also his access tokens):<pre>Authorization: Bearer {client_access_token} Content-Type: application/x-www-form-urlencoded POST /oauth/revoke token={refresh_token}&token_type_hint=refresh_token</pre><p><b>NOTE: The Content-Type of the request must be set to 'application/x-www-form-urlencoded'</b></p>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\AuthorizationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$token = 'token_example'; // string | The token that the client wants to get revoked
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.
$token_type_hint = 'token_type_hint_example'; // string | A hint about the type of the token submitted for revocation

try {
    $apiInstance->revokeToken($token, $x_request_id, $token_type_hint);
} catch (Exception $e) {
    echo 'Exception when calling AuthorizationApi->revokeToken: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **token** | **string**| The token that the client wants to get revoked | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |
| **token_type_hint** | **string**| A hint about the type of the token submitted for revocation | [optional] |

### Return type

void (empty response body)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
