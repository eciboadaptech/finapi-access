# # CreateStandingOrderParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | Identifier of the account that should be used for the order. If you want to do a standalone order (finAPI Payment product, i.e. for an account that is not imported in finAPI) leave this field unset and instead use the fields &lt;code&gt;iban&lt;/code&gt; and &lt;code&gt;bankId&lt;/code&gt;. | [optional]
**iban** | **string** | IBAN of the account that should be used for the order. Use this field only if you want to do a standalone order (finAPI Payment product, i.e. for an account that is not imported in finAPI). Otherwise, use the &lt;code&gt;accountId&lt;/code&gt; field and leave this field unset. | [optional]
**bank_id** | **int** | Identifier of the bank that should be used. Use this field only if you want to do a standalone order (finAPI Payment product, i.e. for an account that is not imported in finAPI) and when the &lt;code&gt;iban&lt;/code&gt; is not sufficient to uniquely identify the bank (a bank search for the IBAN via &lt;code&gt;GET /banks?search&#x3D;[IBAN]&lt;/code&gt; returns multiple banks). If the IBAN uniquely identifies the bank, you may leave this field unset. Also, leave the field unset for non-standalone orders (using the &lt;code&gt;accountId&lt;/code&gt; field). | [optional]
**counterpart_name** | **string** | Name of the counterpart. Note: Neither finAPI nor the involved bank servers are guaranteed to validate the counterpart name. Even if the name does not depict the actual registered account holder of the target account, the order might still be successful.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. |
**counterpart_iban** | **string** | IBAN of the counterpart&#39;s account. |
**amount** | **float** | The amount of the standing order. Must be a positive decimal number with at most two decimal places.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. |
**currency** | [**\OpenAPI\Client\Model\Currency**](Currency.md) |  |
**purpose** | **string** | The purpose of the standing order.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. | [optional]
**sepa_purpose_code** | **string** | SEPA purpose code, according to ISO 20022, external codes set.&lt;br/&gt;Please note that the SEPA purpose code may be ignored by some banks. | [optional]
**end_to_end_id** | **string** | End-To-End ID of the standing order.&lt;br/&gt;Please refer to the &lt;a href&#x3D;&#39;https://documentation.finapi.io/payments/payment-data-validation&#39; target&#x3D;&#39;_blank&#39;&gt; Payment Data Validation documentation &lt;/a&gt; for more details. | [optional]
**start_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Start date of the standing order. Date must be in the future (at least tomorrow). |
**end_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Termination date of the standing order. If provided, it must be after the &#39;startDate&#39;. If not provided, then the standing order will have no termination. | [optional]
**frequency** | [**\OpenAPI\Client\Model\StandingOrderFrequency**](StandingOrderFrequency.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
