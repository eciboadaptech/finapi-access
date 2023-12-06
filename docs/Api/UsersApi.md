# OpenAPI\Client\UsersApi

All URIs are relative to https://sandbox.finapi.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createUser()**](UsersApi.md#createUser) | **POST** /api/v2/users | Create a new user |
| [**deleteAuthorizedUser()**](UsersApi.md#deleteAuthorizedUser) | **DELETE** /api/v2/users | Delete the authorized user |
| [**deleteUnverifiedUser()**](UsersApi.md#deleteUnverifiedUser) | **DELETE** /api/v2/users/{userId} | Delete an unverified user |
| [**editAuthorizedUser()**](UsersApi.md#editAuthorizedUser) | **PATCH** /api/v2/users | Edit the authorized user |
| [**executePasswordChange()**](UsersApi.md#executePasswordChange) | **POST** /api/v2/users/executePasswordChange | Execute password change |
| [**getAuthorizedUser()**](UsersApi.md#getAuthorizedUser) | **GET** /api/v2/users | Get the authorized user |
| [**getVerificationStatus()**](UsersApi.md#getVerificationStatus) | **GET** /api/v2/users/verificationStatus | Get a user&#39;s verification status |
| [**requestPasswordChange()**](UsersApi.md#requestPasswordChange) | **POST** /api/v2/users/requestPasswordChange | Request password change |
| [**verifyUser()**](UsersApi.md#verifyUser) | **POST** /api/v2/users/verify/{userId} | Verify a user |


## `createUser()`

```php
createUser($user_create_params, $x_request_id): \OpenAPI\Client\Model\User
```

Create a new user

<p>Create a new user. Must pass your global (i.e. client) access_token. </p><p>This service returns the user's password as plain text. </p><p>The automatic update of the user's bank connections is disabled by default for any new user. User identifiers are regarded case-insensitive by finAPI.</p><p>Please note that finAPI generally has a restricted set of allowed characters for input fields. You can find the allowed characters <a href = \"https://documentation.finapi.io/access/Allowed-Characters.2764767279.html\">here</a>. If a field does not explicitly specify a set of allowed characters, then these are the characters that are allowed for the field. Some fields may specify a different set of characters, in which case this will be documented for the field (like for the 'id' field in this service).</p>

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_create_params = new \OpenAPI\Client\Model\UserCreateParams(); // \OpenAPI\Client\Model\UserCreateParams | User's details
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->createUser($user_create_params, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->createUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_create_params** | [**\OpenAPI\Client\Model\UserCreateParams**](../Model/UserCreateParams.md)| User&#39;s details | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\User**](../Model/User.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAuthorizedUser()`

```php
deleteAuthorizedUser($psu_ip_address, $psu_device_os, $psu_user_agent, $x_http_method_override, $x_request_id)
```

Delete the authorized user

Delete the authorized user. Must pass the user's access_token. ATTENTION: This deletes the user including all of his bank connections, accounts, balance data and transactions! Also the user's consents will get deleted on the bank's side. THIS PROCESS CANNOT BE UNDONE! Note that a user cannot get deleted while any of his bank connections are currently busy (in the process of import, update, or transaction categorization). <br/><br/>Notes: <br/>&bull; finAPI will send a notification about the deletion of the user to each of your clients that has a user synchronization callback URL set in its configuration. This also includes the client that is performing this request.<br/>&bull; If a consent will get deleted by this service, it's not guaranteed that the consent will also get deleted on the bank's side, as not all banks may support this. Also errors during bank consent deletion will be ignored, so the service won't fail due to this.<br/><br/><b>ATTENTION:</b> For the deletion of XS2A consents, additional headers should be included in the request if the end user is involved. Please refer to the <a href='#general-user-metadata'>User metadata</a> section under 'General Information' of the API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$psu_ip_address = 'psu_ip_address_example'; // string | The IP address of the user's device. This header will be forwarded to the bank on XS2A requests. It has to be an IPv4 address, as some banks cannot work with IPv6 addresses. If a non-IPv4 address is passed, we will replace the value with our own IPv4 address as a fallback.
$psu_device_os = 'psu_device_os_example'; // string | The user's device and/or operating system identification. This header will be forwarded to the bank on XS2A requests.
$psu_user_agent = 'psu_user_agent_example'; // string | The user's web browser or other client device identification. This header will be forwarded to the bank on XS2A requests.
$x_http_method_override = 'x_http_method_override_example'; // string | Some HTTP clients do not support the HTTP methods PATCH or DELETE. If you are using such a client in your application, you can use a POST request instead with this header indicating the originally intended HTTP method. POST Requests having this  header set will be treated either as PATCH or DELETE by the finAPI servers.
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $apiInstance->deleteAuthorizedUser($psu_ip_address, $psu_device_os, $psu_user_agent, $x_http_method_override, $x_request_id);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->deleteAuthorizedUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **psu_ip_address** | **string**| The IP address of the user&#39;s device. This header will be forwarded to the bank on XS2A requests. It has to be an IPv4 address, as some banks cannot work with IPv6 addresses. If a non-IPv4 address is passed, we will replace the value with our own IPv4 address as a fallback. | [optional] |
| **psu_device_os** | **string**| The user&#39;s device and/or operating system identification. This header will be forwarded to the bank on XS2A requests. | [optional] |
| **psu_user_agent** | **string**| The user&#39;s web browser or other client device identification. This header will be forwarded to the bank on XS2A requests. | [optional] |
| **x_http_method_override** | **string**| Some HTTP clients do not support the HTTP methods PATCH or DELETE. If you are using such a client in your application, you can use a POST request instead with this header indicating the originally intended HTTP method. POST Requests having this  header set will be treated either as PATCH or DELETE by the finAPI servers. | [optional] |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

void (empty response body)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteUnverifiedUser()`

```php
deleteUnverifiedUser($user_id, $x_http_method_override, $x_request_id)
```

Delete an unverified user

Delete an unverified user. Must pass your global (i.e. client) access_token.<br/><br/>Notes:<br/>&bull; Unverified users can only exist if the field 'isUserAutoVerificationEnabled' (see Client Configuration Resource) is set to 'false' (or had been false at some point in the past).<br/>&bull; finAPI will send a notification about the deletion of the user to each of your clients that has a user synchronization callback URL set in its configuration. This also includes the client that is performing this request.<br/>&bull; finAPI regards user identifiers case-insensitive.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_id = 'user_id_example'; // string
$x_http_method_override = 'x_http_method_override_example'; // string | Some HTTP clients do not support the HTTP methods PATCH or DELETE. If you are using such a client in your application, you can use a POST request instead with this header indicating the originally intended HTTP method. POST Requests having this  header set will be treated either as PATCH or DELETE by the finAPI servers.
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $apiInstance->deleteUnverifiedUser($user_id, $x_http_method_override, $x_request_id);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->deleteUnverifiedUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_id** | **string**|  | |
| **x_http_method_override** | **string**| Some HTTP clients do not support the HTTP methods PATCH or DELETE. If you are using such a client in your application, you can use a POST request instead with this header indicating the originally intended HTTP method. POST Requests having this  header set will be treated either as PATCH or DELETE by the finAPI servers. | [optional] |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

void (empty response body)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `editAuthorizedUser()`

```php
editAuthorizedUser($user_update_params, $x_http_method_override, $x_request_id): \OpenAPI\Client\Model\User
```

Edit the authorized user

Edit the authorized user's data and settings. Must pass the user's access_token. Pass an empty string (but not null) to unset either the email or phone number. At least one field must have a non-null value in the request body. This service returns the user's password as 'XXXXX'.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_update_params = new \OpenAPI\Client\Model\UserUpdateParams(); // \OpenAPI\Client\Model\UserUpdateParams | User's details
$x_http_method_override = 'x_http_method_override_example'; // string | Some HTTP clients do not support the HTTP methods PATCH or DELETE. If you are using such a client in your application, you can use a POST request instead with this header indicating the originally intended HTTP method. POST Requests having this  header set will be treated either as PATCH or DELETE by the finAPI servers.
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->editAuthorizedUser($user_update_params, $x_http_method_override, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->editAuthorizedUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_update_params** | [**\OpenAPI\Client\Model\UserUpdateParams**](../Model/UserUpdateParams.md)| User&#39;s details | |
| **x_http_method_override** | **string**| Some HTTP clients do not support the HTTP methods PATCH or DELETE. If you are using such a client in your application, you can use a POST request instead with this header indicating the originally intended HTTP method. POST Requests having this  header set will be treated either as PATCH or DELETE by the finAPI servers. | [optional] |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\User**](../Model/User.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `executePasswordChange()`

```php
executePasswordChange($execute_password_change_params, $x_request_id)
```

Execute password change

Change the password of a user. Must pass your global (i.e. client) access_token.<br/><br/>Note: When changing the password of a user, all tokens that have been handed out for that user (for whatever client) will be revoked! Also note that finAPI regards user identifiers case-insensitive.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$execute_password_change_params = new \OpenAPI\Client\Model\ExecutePasswordChangeParams(); // \OpenAPI\Client\Model\ExecutePasswordChangeParams
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $apiInstance->executePasswordChange($execute_password_change_params, $x_request_id);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->executePasswordChange: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **execute_password_change_params** | [**\OpenAPI\Client\Model\ExecutePasswordChangeParams**](../Model/ExecutePasswordChangeParams.md)|  | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

void (empty response body)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAuthorizedUser()`

```php
getAuthorizedUser($x_request_id): \OpenAPI\Client\Model\User
```

Get the authorized user

Get the authorized user's data. Must pass the user's access_token. Only the authorized user can get his data, i.e. his access_token must be used. This service returns the user's password as 'XXXXX'.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->getAuthorizedUser($x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getAuthorizedUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\User**](../Model/User.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVerificationStatus()`

```php
getVerificationStatus($user_id, $x_request_id): \OpenAPI\Client\Model\VerificationStatusResource
```

Get a user's verification status

Get the verification status of the requested user. Must pass your global (i.e. client) access_token. Note that finAPI regards user identifiers case-insensitive.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_id = 'user_id_example'; // string | User's identifier
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->getVerificationStatus($user_id, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->getVerificationStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_id** | **string**| User&#39;s identifier | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\VerificationStatusResource**](../Model/VerificationStatusResource.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `requestPasswordChange()`

```php
requestPasswordChange($request_password_change_params, $x_request_id): \OpenAPI\Client\Model\PasswordChangingResource
```

Request password change

Request password change for a user. Must pass your global (i.e. client) access_token. Note that finAPI regards user identifiers case-insensitive.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$request_password_change_params = new \OpenAPI\Client\Model\RequestPasswordChangeParams(); // \OpenAPI\Client\Model\RequestPasswordChangeParams
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->requestPasswordChange($request_password_change_params, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->requestPasswordChange: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **request_password_change_params** | [**\OpenAPI\Client\Model\RequestPasswordChangeParams**](../Model/RequestPasswordChangeParams.md)|  | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\PasswordChangingResource**](../Model/PasswordChangingResource.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `verifyUser()`

```php
verifyUser($user_id, $x_request_id)
```

Verify a user

Verify a user. User verification is only required when your client does not have auto-verification enabled (see field 'isUserAutoVerificationEnabled' in Client Configuration Resource). Must pass your global (i.e. client) access_token. Note that finAPI regards user identifiers case-insensitive.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\UsersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$user_id = 'user_id_example'; // string | User's identifier
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $apiInstance->verifyUser($user_id, $x_request_id);
} catch (Exception $e) {
    echo 'Exception when calling UsersApi->verifyUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **user_id** | **string**| User&#39;s identifier | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

void (empty response body)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
