# # ErrorMessage

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**errors** | [**\OpenAPI\Client\Model\ErrorDetails[]**](ErrorDetails.md) | List of errors&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; ErrorDetails |
**date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Server date of when the error(s) occurred |
**request_id** | **string** | ID of the request that caused this error. This is either what you have passed for the header &#39;X-Request-Id&#39;, or an auto-generated ID in case you didn&#39;t pass any value for that header.&lt;br/&gt;&lt;br/&gt; |
**endpoint** | **string** | The service endpoint that was called |
**auth_context** | **string** | Information about the authorization context of the service call |
**bank** | **string** | BLZ and name (in format \&quot;&lt;BLZ&gt; - &lt;name&gt;\&quot;) of a bank that was used for the original request | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
