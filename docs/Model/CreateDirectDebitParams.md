# # CreateDirectDebitParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**single_booking** | **bool** | This field is only relevant when you pass multiple orders. It determines whether the orders should be processed by the bank as one collective booking (in case of &#39;false&#39;), or as single bookings (in case of &#39;true&#39;). Note that it is subject to the bank whether it will regard the field. Default value is &#39;false&#39;. | [optional] [default to false]
**account_id** | **int** | Identifier of the account that should be used for the direct debit. |
**direct_debit_type** | [**\OpenAPI\Client\Model\DirectDebitType**](DirectDebitType.md) |  |
**sequence_type** | [**\OpenAPI\Client\Model\DirectDebitSequenceType**](DirectDebitSequenceType.md) |  |
**direct_debits** | [**\OpenAPI\Client\Model\DirectDebitOrderParams[]**](DirectDebitOrderParams.md) | List of direct debit orders (may contain at most 15000 items). Please note that collective direct debit may not always be supported.&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; DirectDebitOrderParams |
**execution_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Execution date for the direct debit(s). May not be in the past. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
