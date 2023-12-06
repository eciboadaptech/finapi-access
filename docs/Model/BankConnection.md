# # BankConnection

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Bank connection identifier |
**name** | **string** | Custom name for the bank connection. You can set this field with the &#39;Edit a bank connection&#39; service, as well as during the initial import of the bank connection. | [optional]
**update_status** | **string** | Current status of data download (account balances and transactions/securities). The POST /bankConnections/import and POST /bankConnections/&lt;id&gt;/update services will set this flag to IN_PROGRESS before they return. Once the import or update has finished, the status will be changed to READY. |
**categorization_status** | [**\OpenAPI\Client\Model\CategorizationStatus**](CategorizationStatus.md) |  |
**interfaces** | [**\OpenAPI\Client\Model\BankConnectionInterface[]**](BankConnectionInterface.md) | Set of interfaces that are connected for this bank connection.&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; BankConnectionInterface |
**account_ids** | **int[]** | Identifiers of the accounts that belong to this bank connection |
**owners** | [**\OpenAPI\Client\Model\BankConnectionOwner[]**](BankConnectionOwner.md) | Information about the owner(s) of the bank connection&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; BankConnectionOwner | [optional]
**bank** | [**\OpenAPI\Client\Model\BankConnectionBank**](BankConnectionBank.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
