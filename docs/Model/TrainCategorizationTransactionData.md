# # TrainCategorizationTransactionData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_type_id** | **int** | Identifier of account type.&lt;br/&gt;&lt;br/&gt;1 &#x3D; Checking,&lt;br/&gt;2 &#x3D; Savings,&lt;br/&gt;3 &#x3D; CreditCard,&lt;br/&gt;4 &#x3D; Security,&lt;br/&gt;5 &#x3D; Loan,&lt;br/&gt;7 &#x3D; Membership,&lt;br/&gt;8 &#x3D; Bausparen&lt;br/&gt;&lt;br/&gt; |
**amount** | **float** | Amount |
**purpose** | **string** | Purpose. Any symbols are allowed. Default value: null. | [optional]
**counterpart** | **string** | Counterpart. Any symbols are allowed. Default value: null. | [optional]
**counterpart_iban** | **string** | Counterpart IBAN. Default value: null. | [optional]
**counterpart_account_number** | **string** | Counterpart account number. Default value: null. | [optional]
**counterpart_blz** | **string** | Counterpart BLZ. Default value: null. | [optional]
**counterpart_bic** | **string** | Counterpart BIC. Default value: null. | [optional]
**mc_code** | **string** | Merchant category code (for credit card transactions only). Default value: null. NOTE: This field is currently not regarded. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
