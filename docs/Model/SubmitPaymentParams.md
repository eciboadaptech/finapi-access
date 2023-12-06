# # SubmitPaymentParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**payment_id** | **int** | Payment identifier |
**banking_interface** | [**\OpenAPI\Client\Model\BankingInterface**](BankingInterface.md) |  |
**login_credentials** | [**\OpenAPI\Client\Model\LoginCredential[]**](LoginCredential.md) | Login credentials. May not be required when the credentials are stored in finAPI, or when the bank interface has no login credentials.&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; LoginCredential | [optional]
**redirect_url** | **string** | Must only be passed when the used interface has the property REDIRECT_APPROACH. The user will be redirected to the given URL from the bank&#39;s website after completing the bank login and (possibly) the SCA. | [optional]
**multi_step_authentication** | [**\OpenAPI\Client\Model\ConnectInterfaceParamsMultiStepAuthentication**](ConnectInterfaceParamsMultiStepAuthentication.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
