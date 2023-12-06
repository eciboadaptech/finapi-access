# OpenAPI\Client\StandingOrdersApi

All URIs are relative to https://sandbox.finapi.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createStandingOrder()**](StandingOrdersApi.md#createStandingOrder) | **POST** /api/v2/standingOrders | Create a standing order |
| [**getStandingOrders()**](StandingOrdersApi.md#getStandingOrders) | **GET** /api/v2/standingOrders | Get standing orders |
| [**submitStandingOrder()**](StandingOrdersApi.md#submitStandingOrder) | **POST** /api/v2/standingOrders/submit | Submit standing order |


## `createStandingOrder()`

```php
createStandingOrder($create_standing_order_params, $x_request_id): \OpenAPI\Client\Model\StandingOrder
```

Create a standing order

To use this service PIS must be enabled by our customer support for your client.<br/><br/>If you are unlicensed, or licensed but using finAPI’s Web Form, this endpoint is not relevant to you. Please use the endpoint <a href='?product=web_form_2.0#post-/api/webForms/standingOrder' target='_blank'> here</a> to initiate (create and also submit) standing orders!<br/><br/>Note that this service only creates a standing order resource in finAPI and there is no bank communication involved.<br/>To submit the standing order to the bank, call the 'Submit standing order' service

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\StandingOrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$create_standing_order_params = new \OpenAPI\Client\Model\CreateStandingOrderParams(); // \OpenAPI\Client\Model\CreateStandingOrderParams | Create standing order parameters
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->createStandingOrder($create_standing_order_params, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StandingOrdersApi->createStandingOrder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **create_standing_order_params** | [**\OpenAPI\Client\Model\CreateStandingOrderParams**](../Model/CreateStandingOrderParams.md)| Create standing order parameters | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\StandingOrder**](../Model/StandingOrder.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getStandingOrders()`

```php
getStandingOrders($ids, $account_ids, $min_amount, $max_amount, $status, $page, $per_page, $order, $x_request_id): \OpenAPI\Client\Model\PageableStandingOrderResources
```

Get standing orders

Get standing orders of the user that is authorized by the access_token. Must pass the user's access_token.<br/><br/><br/>Web Form 2.0 customers should also use this endpoint to learn about the status of the standing order initiation. (The Standing Order ID can be found in the payload of the API response from the relevant Web Form 2.0 API endpoint).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\StandingOrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ids = array(56); // int[] | A comma-separated list of standing order identifiers. If specified, then only standing orders whose identifier is matching any of the given identifiers will be regarded. The maximum number of identifiers is 1000.
$account_ids = array(56); // int[] | A comma-separated list of account identifiers. If specified, then only standing orders that relate to the given account(s) will be regarded. The maximum number of identifiers is 1000.
$min_amount = 3.4; // float | If specified, then only those standing orders are regarded whose (absolute) total amount is equal or greater than the given amount will be regarded. The value must be a positive (absolute) amount.
$max_amount = 3.4; // float | If specified, then only those standing orders are regarded whose (absolute) total amount is equal or less than the given amount will be regarded. Value must be a positive (absolute) amount.
$status = array('status_example'); // string[] | A comma-separated list of standing order statuses. If provided, then only standing orders whose status is matching any of the given statuses will be returned. Allowed values: 'OPEN', 'PENDING', 'SUCCESSFUL', 'NOT_SUCCESSFUL' or 'DISCARDED'. Example: 'OPEN,PENDING'.
$page = 1; // int | Result page that you want to retrieve
$per_page = 20; // int | Maximum number of records per page. By default it's 20.
$order = array('order_example'); // string[] | Determines the order of the results. You can use the following fields for ordering the response: 'id', 'amount', 'requestDate', 'requestCompletionDate'. The default order for all services is 'id,asc'.
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->getStandingOrders($ids, $account_ids, $min_amount, $max_amount, $status, $page, $per_page, $order, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StandingOrdersApi->getStandingOrders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ids** | [**int[]**](../Model/int.md)| A comma-separated list of standing order identifiers. If specified, then only standing orders whose identifier is matching any of the given identifiers will be regarded. The maximum number of identifiers is 1000. | [optional] |
| **account_ids** | [**int[]**](../Model/int.md)| A comma-separated list of account identifiers. If specified, then only standing orders that relate to the given account(s) will be regarded. The maximum number of identifiers is 1000. | [optional] |
| **min_amount** | **float**| If specified, then only those standing orders are regarded whose (absolute) total amount is equal or greater than the given amount will be regarded. The value must be a positive (absolute) amount. | [optional] |
| **max_amount** | **float**| If specified, then only those standing orders are regarded whose (absolute) total amount is equal or less than the given amount will be regarded. Value must be a positive (absolute) amount. | [optional] |
| **status** | [**string[]**](../Model/string.md)| A comma-separated list of standing order statuses. If provided, then only standing orders whose status is matching any of the given statuses will be returned. Allowed values: &#39;OPEN&#39;, &#39;PENDING&#39;, &#39;SUCCESSFUL&#39;, &#39;NOT_SUCCESSFUL&#39; or &#39;DISCARDED&#39;. Example: &#39;OPEN,PENDING&#39;. | [optional] |
| **page** | **int**| Result page that you want to retrieve | [optional] [default to 1] |
| **per_page** | **int**| Maximum number of records per page. By default it&#39;s 20. | [optional] [default to 20] |
| **order** | [**string[]**](../Model/string.md)| Determines the order of the results. You can use the following fields for ordering the response: &#39;id&#39;, &#39;amount&#39;, &#39;requestDate&#39;, &#39;requestCompletionDate&#39;. The default order for all services is &#39;id,asc&#39;. | [optional] |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\PageableStandingOrderResources**](../Model/PageableStandingOrderResources.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `submitStandingOrder()`

```php
submitStandingOrder($submit_standing_order_params, $psu_ip_address, $psu_device_os, $psu_user_agent, $x_request_id): \OpenAPI\Client\Model\StandingOrder
```

Submit standing order

To use this service PIS must be enabled by our customer support for your client.<br/><br/>If you are unlicensed, or licensed but using finAPI’s Web Form, this endpoint is not relevant to you. Please use the endpoint <a href='?product=web_form_2.0#post-/api/webForms/standingOrder' target='_blank'> here</a> to initiate (create and also submit) standing orders!<br/><br/>Submit a standing order to the bank which was previously created with the 'Create a standing order' service.<br/><br/>Before you submit the standing order, please check that the given bank interface supports the required PIS capabilities, otherwise the standing order could get rejected.<br/>In case the standing order is initiated from a given IBAN, please refer to the field BankInterface.paymentCapabilities to be sure the standing order you are creating is currently supported by the bank.<br/><br/>Usually banks require a multi-step authentication to authorize the standing order. In this case, and if the finAPI Web Form flow is not used, the service will respond with HTTP code 510 and an error object containing a multiStepAuthentication object which describes the necessary next authentication steps. You must then retry the service call, passing the same arguments plus an additional 'multiStepAuthentication' element.<br/>Please refer to the description of the HTTP 510 error code below and the documentation of the 'MultiStepAuthenticationCallback' response object for details.<br/><br/><b>ATTENTION:</b> For XS2A interface additional headers must be included in the request if the end user is involved. Please refer to the <a href='#general-user-metadata'>User metadata</a> section under 'General Information' of the API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\StandingOrdersApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$submit_standing_order_params = new \OpenAPI\Client\Model\SubmitStandingOrderParams(); // \OpenAPI\Client\Model\SubmitStandingOrderParams | Parameters for standing order submission
$psu_ip_address = 'psu_ip_address_example'; // string | The IP address of the user's device. This header will be forwarded to the bank on XS2A requests. It has to be an IPv4 address, as some banks cannot work with IPv6 addresses. If a non-IPv4 address is passed, we will replace the value with our own IPv4 address as a fallback.
$psu_device_os = 'psu_device_os_example'; // string | The user's device and/or operating system identification. This header will be forwarded to the bank on XS2A requests.
$psu_user_agent = 'psu_user_agent_example'; // string | The user's web browser or other client device identification. This header will be forwarded to the bank on XS2A requests.
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->submitStandingOrder($submit_standing_order_params, $psu_ip_address, $psu_device_os, $psu_user_agent, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling StandingOrdersApi->submitStandingOrder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **submit_standing_order_params** | [**\OpenAPI\Client\Model\SubmitStandingOrderParams**](../Model/SubmitStandingOrderParams.md)| Parameters for standing order submission | |
| **psu_ip_address** | **string**| The IP address of the user&#39;s device. This header will be forwarded to the bank on XS2A requests. It has to be an IPv4 address, as some banks cannot work with IPv6 addresses. If a non-IPv4 address is passed, we will replace the value with our own IPv4 address as a fallback. | [optional] |
| **psu_device_os** | **string**| The user&#39;s device and/or operating system identification. This header will be forwarded to the bank on XS2A requests. | [optional] |
| **psu_user_agent** | **string**| The user&#39;s web browser or other client device identification. This header will be forwarded to the bank on XS2A requests. | [optional] |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\StandingOrder**](../Model/StandingOrder.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
