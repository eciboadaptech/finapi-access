# # AccountParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_name** | **string** | Account name. | [optional]
**account_type** | [**\OpenAPI\Client\Model\AccountType**](AccountType.md) |  | [optional]
**is_new** | **bool** | Whether this account should be flagged as &#39;new&#39; or not. Any newly imported account will have this flag initially set to true, and remain so until you set it to false (see PATCH /accounts/&lt;id&gt;). How you use this field is up to your interpretation, however it is recommended to set the flag to false for all accounts right after the initial import of the bank connection. This way, you will be able to recognize accounts that get newly imported during a later update of the bank connection, by checking for any accounts with the flag set to &#39;true&#39; after every update of the bank connection. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
