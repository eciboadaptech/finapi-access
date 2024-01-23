# # SepaMoneyTransferConstraints

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**mandatory_fields** | [**\OpenAPI\Client\Model\SepaMoneyTransferMandatoryFields**](SepaMoneyTransferMandatoryFields.md) |  | [optional]
**purpose_or_end_to_end_id** | **bool** | Indicates whether the bank exclusively supports either the &#39;purpose&#39; or the &#39;endToEndId&#39; for SEPA money transfers, but not both within the same request. | [optional]
**max_collective_orders** | **int** | The maximum number of orders that the bank allows for a SEPA collective money transfer. | [optional]
**max_purpose_length** | **int** | The maximum allowed chars of purpose for a SEPA money transfer. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
