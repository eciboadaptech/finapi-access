# # BankConnectionInterfaceLastManualUpdate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**result** | [**\OpenAPI\Client\Model\UpdateResultStatus**](UpdateResultStatus.md) |  |
**error_message** | **string** | In case the update result is not &lt;code&gt;OK&lt;/code&gt;, this field may contain an error message with details about why the update failed (it is not guaranteed that a message is available though). In case the update result is &lt;code&gt;OK&lt;/code&gt;, the field will always be null. | [optional]
**error_type** | [**\OpenAPI\Client\Model\ErrorType**](ErrorType.md) |  | [optional]
**timestamp** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Time of the update. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
