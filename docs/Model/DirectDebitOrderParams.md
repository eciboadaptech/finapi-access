# # DirectDebitOrderParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**counterpart_name** | **string** | Name of the counterpart. Note: Neither finAPI nor the involved bank servers are guaranteed to validate the counterpart name. Even if the name does not depict the actual registered account holder of the target account, the order might still be successful.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. |
**counterpart_iban** | **string** | IBAN of the counterpart&#39;s account. |
**counterpart_bic** | **string** | BIC of the counterpart&#39;s account. Only required when there is no &#39;IBAN_ONLY&#39;-capability in the respective account/interface combination that is to be used when submitting the payment. | [optional]
**amount** | **float** | The amount of the payment. Must be a positive decimal number with at most two decimal places. When debiting money using the FINTS_SERVER or WEB_SCRAPER interface, the currency is always EUR.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. |
**purpose** | **string** | The purpose of the transfer transaction.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. | [optional]
**sepa_purpose_code** | **string** | SEPA purpose code, according to ISO 20022, external codes set.&lt;br/&gt;Please note that the SEPA purpose code may be ignored by some banks. | [optional]
**end_to_end_id** | **string** | End-To-End ID for the transfer transaction.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. | [optional]
**mandate_id** | **string** | Mandate ID that this direct debit order is based on. |
**mandate_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Date of the mandate that this direct debit order is based on |
**creditor_id** | **string** | Creditor ID of the source account&#39;s holder |
**counterpart_address** | **string** | The postal address of the debtor. This should be defined for direct debits created for debtors outside of the european union. | [optional]
**counterpart_country** | [**\OpenAPI\Client\Model\ISO3166Alpha2Codes**](ISO3166Alpha2Codes.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
