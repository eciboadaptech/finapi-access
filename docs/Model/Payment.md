# # Payment

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Payment identifier |
**account_id** | **int** | Identifier of the account to which this payment relates. This field is only set if it was specified upon creation of the payment. | [optional]
**iban** | **string** | IBAN of the account to which this payment relates. This field is only set if it was specified upon creation of the payment. | [optional]
**bank_id** | **int** | Identifier of the bank to which this payment relates. |
**type** | [**\OpenAPI\Client\Model\PaymentType**](PaymentType.md) |  |
**amount** | **float** | Total money amount of the payment order(s), as absolute value |
**order_count** | **int** | Total count of orders included in this payment |
**status** | [**\OpenAPI\Client\Model\OrderInitiationStatus**](OrderInitiationStatus.md) |  |
**bank_message** | **string** | The bank&#39;s response to the most recent request for this payment. Possible requests are: Initial submission of the payment, execution request or subsequent status checks. Note that this field may not always (or never) be set. Also, as long as the payment has not reached its final status, this field can always change. | [optional]
**request_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Time of when finAPI submitted this payment to the bank. | [optional]
**execution_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Time of when the execution of this payment has completed.&lt;br/&gt;&lt;br/&gt;Note:&lt;br/&gt;&amp;bull; When the execution of a payment has completed, it does not necessarily mean that the payment was successful. Please refer to the payment &#39;status&#39; for its final status.&lt;br/&gt;&amp;bull; The execution date may deviate from the date when the bank will actually book the payment (for example if the &#39;instructedExecutionDate&#39; is in the future). | [optional]
**instructed_execution_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;The date that was specified as &#39;executionDate&#39; upon creation of the payment. This field may not be set if no &#39;executionDate&#39; was specified upon payment creation. | [optional]
**instant_payment** | **bool** | Whether the order was submitted to the bank as an instant SEPA order. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
