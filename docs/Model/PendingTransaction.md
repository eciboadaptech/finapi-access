# # PendingTransaction

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Pending transaction identifier |
**account_id** | **int** | Account identifier |
**import_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Date of transaction import. |
**value_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Value date.&lt;br/&gt;&lt;br/&gt;&lt;strong&gt;NOTE:&lt;/strong&gt; In case the bank does not deliver any date information for the transaction, finAPI will use the current date (i.e. date of import). |
**bank_booking_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Bank booking date. | [optional]
**amount** | **float** | Transaction amount |
**currency** | [**\OpenAPI\Client\Model\Currency**](Currency.md) |  | [optional]
**purpose** | **string** | Transaction purpose. Maximum length: 2000 | [optional]
**counterparty_name** | **string** | Counterparty name. Maximum length: 80 | [optional]
**counterparty_iban** | **string** | Counterparty IBAN | [optional]
**counterparty_account_number** | **string** | Counterparty account number | [optional]
**counterparty_blz** | **string** | Counterparty BLZ | [optional]
**counterparty_bic** | **string** | Counterparty BIC | [optional]
**counterparty_bank_name** | **string** | Counterparty Bank name | [optional]
**counterparty_mandate_reference** | **string** | The mandate reference of the counterparty | [optional]
**counterparty_customer_reference** | **string** | The customer reference of the counterparty | [optional]
**counterparty_creditor_id** | **string** | The creditor ID of the counterparty. Exists only for SEPA direct debit transactions (\&quot;Lastschrift\&quot;). | [optional]
**counterparty_debtor_id** | **string** | The originator&#39;s identification code. Exists only for SEPA money transfer transactions (\&quot;Überweisung\&quot;). | [optional]
**end_to_end_id** | **string** | End-To-End ID | [optional]
**type** | **string** | Transaction type, according to the bank. If set, this will contain a term in the language of the bank, that you can display to the user. Some examples of common values are: \&quot;Lastschrift\&quot;, \&quot;Auslands&amp;uuml;berweisung\&quot;, \&quot;Geb&amp;uuml;hren\&quot;, \&quot;Zinsen\&quot;. The maximum possible length of this field is 255 characters. | [optional]
**type_code_zka** | **string** | ZKA business transaction code which relates to the transaction&#39;s type. Possible values range from 1 through 999. If no information about the ZKA type code is available, then this field will be null. | [optional]
**type_code_swift** | **string** | SWIFT transaction type code. If no information about the SWIFT code is available, then this field will be null. | [optional]
**sepa_purpose_code** | **string** | SEPA purpose code, according to ISO 20022 | [optional]
**bank_transaction_code** | **string** | Bank transaction code, according to ISO 20022 | [optional]
**primanota** | **string** | Transaction primanota (bank side identification number) | [optional]
**compensation_amount** | **float** | Compensation Amount. Sum of reimbursement of out-of-pocket expenses plus processing brokerage in case of a national return / refund debit as well as an optional interest equalisation. Exists predominantly for SEPA direct debit returns. | [optional]
**original_amount** | **float** | Original Amount of the original direct debit. Exists predominantly for SEPA direct debit returns. | [optional]
**original_currency** | [**\OpenAPI\Client\Model\Currency**](Currency.md) |  | [optional]
**fee_amount** | **float** | Amount of the transaction fee. Some banks charge a specific fee per transaction. Only returned by a few banks. | [optional]
**fee_currency** | [**\OpenAPI\Client\Model\Currency**](Currency.md) |  | [optional]
**different_debtor** | **string** | Payer&#39;s/debtor&#39;s reference party (in the case of a credit transfer) or payee&#39;s/creditor&#39;s reference party (in the case of a direct debit) | [optional]
**different_creditor** | **string** | Payee&#39;s/creditor&#39;s reference party (in the case of a credit transfer) or payer&#39;s/debtor&#39;s reference party (in the case of a direct debit) | [optional]
**paypal_data** | [**\OpenAPI\Client\Model\PendingTransactionPaypalData**](PendingTransactionPaypalData.md) |  | [optional]
**certis_data** | [**\OpenAPI\Client\Model\PendingTransactionCertisData**](PendingTransactionCertisData.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
