# # MultiStepAuthenticationChallenge

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hash** | **string** | Hash for this multi-step authentication flow. Must be passed back to finAPI when continuing the flow. |
**status** | [**\OpenAPI\Client\Model\MsaStatus**](MsaStatus.md) |  |
**challenge_message** | **string** | In case of status &#x3D; CHALLENGE_RESPONSE_REQUIRED, this field contains a message from the bank containing instructions for the user on how to proceed with the authorization. | [optional]
**answer_field_label** | **string** | Suggestion from the bank on how you can label your input field where the user should enter his challenge response. | [optional]
**redirect_url** | **string** | In case of status &#x3D; REDIRECT_REQUIRED, this field contains the URL to which you must direct the user. It already includes the redirect URL back to your client that you have passed when initiating the service call. | [optional]
**redirect_context** | **string** | Set in case of status &#x3D; REDIRECT_REQUIRED. When the bank redirects the user back to your client, the redirect URL will contain this string, which you must process to identify the user context for the callback on your side. | [optional]
**redirect_context_field** | **string** | Set in case of status &#x3D; REDIRECT_REQUIRED. This field is set to the name of the query parameter that contains the &#39;redirectContext&#39; in the redirect URL from the bank back to your client. | [optional]
**two_step_procedures** | [**\OpenAPI\Client\Model\TwoStepProcedure[]**](TwoStepProcedure.md) | In case of status &#x3D; TWO_STEP_PROCEDURE_REQUIRED, this field contains the available two-step procedures. Note that this set does not necessarily match the set that is stored in the respective bank connection interface. You should always use the set from this field for the multi-step authentication flow.&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; TwoStepProcedure | [optional]
**photo_tan_mime_type** | **string** | In case that the &#39;photoTanData&#39; field is set (i.e. not null), this field contains the MIME type to use for interpreting the photo data (e.g.: &#39;image/png&#39;) | [optional]
**photo_tan_data** | **string** | In case that the bank server has instructed the user to scan a photo (or more generally speaking, any kind of QR-code-like data), then this field will contain the raw data of the photo as a BASE-64 string. | [optional]
**optical_data** | **string** | In case that the bank server has instructed the user to scan a flicker code, then this field will contain the raw data for the flicker animation as a BASE-64 string. | [optional]
**optical_data_as_reiner_sct** | **bool** | This field is only relevant when the field &#39;opticalData&#39; is set. It depicts whether the optical data should be processed with the use of the Reiner SCT flicker algorithm. For more details, see: &lt;a href&#x3D;&#39;https://documentation.finapi.io/access/Flicker-Code-Template.2807824454.html&#39; target&#x3D;&#39;_blank&#39;&gt;Flicker Code Template&lt;/a&gt; |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
