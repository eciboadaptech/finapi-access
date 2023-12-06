# OpenAPI\Client\PendingTransactionsApi

All URIs are relative to https://sandbox.finapi.io, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAndSearchAllPendingTransactions()**](PendingTransactionsApi.md#getAndSearchAllPendingTransactions) | **GET** /api/v2/pendingTransactions | Get and search all pending transactions |
| [**getPendingTransaction()**](PendingTransactionsApi.md#getPendingTransaction) | **GET** /api/v2/pendingTransactions/{id} | Get a pending transaction |


## `getAndSearchAllPendingTransactions()`

```php
getAndSearchAllPendingTransactions($ids, $account_ids, $page, $per_page, $order, $x_request_id): \OpenAPI\Client\Model\PageablePendingTransactionResources
```

Get and search all pending transactions

Get pending transactions of the user that is authorized by the access_token. Must pass the user's access_token. You can set optional search criteria to get only those pending transactions that you are interested in. If you do not specify any search criteria, then this service functions as a 'get all' service.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\PendingTransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$ids = array(56); // int[] | A comma-separated list of pending transaction identifiers. If specified, then only pending transactions whose identifier match any of the given identifiers will be regarded. The maximum number of identifiers is 1000.
$account_ids = array(56); // int[] | A comma-separated list of account identifiers. If specified, then only pending transactions that relate to the given accounts will be regarded. If not specified, then all accounts will be regarded.
$page = 1; // int | Result page that you want to retrieve.
$per_page = 20; // int | Maximum number of records per page. By default it's 20.
$order = array('order_example'); // string[] | Determines the order of the results. You can use the following fields for ordering the response: 'id', 'accountId', 'valueDate', 'bankBookingDate', 'importDate' and 'amount'. The default order for all services is 'id,asc'. You can also order by multiple properties. In that case the order of the parameters passed is important. Example: '/pendingTransactions?order=valueDate,desc&order=counterpartyName' will return the latest pending transactions first. If there are more pending transactions on the same day, then these pending transactions are ordered by the counterparty name (ascending). The general format is: 'property[,asc|desc]', with 'asc' being the default value.
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->getAndSearchAllPendingTransactions($ids, $account_ids, $page, $per_page, $order, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PendingTransactionsApi->getAndSearchAllPendingTransactions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **ids** | [**int[]**](../Model/int.md)| A comma-separated list of pending transaction identifiers. If specified, then only pending transactions whose identifier match any of the given identifiers will be regarded. The maximum number of identifiers is 1000. | [optional] |
| **account_ids** | [**int[]**](../Model/int.md)| A comma-separated list of account identifiers. If specified, then only pending transactions that relate to the given accounts will be regarded. If not specified, then all accounts will be regarded. | [optional] |
| **page** | **int**| Result page that you want to retrieve. | [optional] [default to 1] |
| **per_page** | **int**| Maximum number of records per page. By default it&#39;s 20. | [optional] [default to 20] |
| **order** | [**string[]**](../Model/string.md)| Determines the order of the results. You can use the following fields for ordering the response: &#39;id&#39;, &#39;accountId&#39;, &#39;valueDate&#39;, &#39;bankBookingDate&#39;, &#39;importDate&#39; and &#39;amount&#39;. The default order for all services is &#39;id,asc&#39;. You can also order by multiple properties. In that case the order of the parameters passed is important. Example: &#39;/pendingTransactions?order&#x3D;valueDate,desc&amp;order&#x3D;counterpartyName&#39; will return the latest pending transactions first. If there are more pending transactions on the same day, then these pending transactions are ordered by the counterparty name (ascending). The general format is: &#39;property[,asc|desc]&#39;, with &#39;asc&#39; being the default value. | [optional] |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\PageablePendingTransactionResources**](../Model/PageablePendingTransactionResources.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPendingTransaction()`

```php
getPendingTransaction($id, $x_request_id): \OpenAPI\Client\Model\PendingTransaction
```

Get a pending transaction

Get a single pending transaction of the user that is authorized by the access_token. Must pass the pending transaction's identifier and the user's access_token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');

// Configure OAuth2 access token for authorization: finapi_auth
$config = OpenAPI\Client\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new OpenAPI\Client\Api\PendingTransactionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = 56; // int | Identifier of pending transaction
$x_request_id = 'x_request_id_example'; // string | With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don't pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name 'X-Request-Id'. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster.

try {
    $result = $apiInstance->getPendingTransaction($id, $x_request_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PendingTransactionsApi->getPendingTransaction: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **id** | **int**| Identifier of pending transaction | |
| **x_request_id** | **string**| With any API call, you can pass a request ID. The request ID can be an arbitrary string with up to 255 characters. Passing a longer string will result in an error. If you don&#39;t pass a request ID for a call, finAPI will generate a random ID internally. The request ID is always returned back in the response of a service, as a header with name &#39;X-Request-Id&#39;. We highly recommend to always pass a (preferably unique) request ID, and include it into your client application logs whenever you make a request or receive a response (especially in the case of an error response). finAPI is also logging request IDs on its end. Having a request ID can help the finAPI support team to work more efficiently and solve tickets faster. | [optional] |

### Return type

[**\OpenAPI\Client\Model\PendingTransaction**](../Model/PendingTransaction.md)

### Authorization

[finapi_auth](../../README.md#finapi_auth), [finapi_auth](../../README.md#finapi_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
