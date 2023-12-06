# # Security

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Identifier. Note: Whenever a security account is being updated, its security positions will be internally re-created, meaning that the identifier of a security position might change over time. |
**account_id** | **int** | Security account identifier |
**name** | **string** | Name | [optional]
**isin** | **string** | ISIN | [optional]
**wkn** | **string** | WKN | [optional]
**quote** | **float** | Quote | [optional]
**quote_currency** | **string** | Currency of quote | [optional]
**quote_type** | [**\OpenAPI\Client\Model\SecurityPositionQuoteType**](SecurityPositionQuoteType.md) |  | [optional]
**quote_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Quote date. | [optional]
**quantity_nominal** | **float** | Value of quantity or nominal | [optional]
**quantity_nominal_type** | [**\OpenAPI\Client\Model\SecurityPositionQuantityNominalType**](SecurityPositionQuantityNominalType.md) |  | [optional]
**market_value** | **float** | Market value | [optional]
**market_value_currency** | **string** | Currency of market value | [optional]
**entry_quote** | **float** | Entry quote | [optional]
**entry_quote_currency** | **string** | Currency of entry quote | [optional]
**profit_or_loss** | **float** | Current profit or loss | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
