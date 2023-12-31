# # NotificationRuleParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**trigger_event** | **string** | Trigger event type |
**params** | **array<string,string>** | Additional parameters that are specific to the chosen trigger event type. The specifics of the different trigger events are documented &lt;a href&#x3D;&#39;https://documentation.finapi.io/access/Push-Notifications-(Web-Hooks).2766405696.html&#39; target&#x3D;&#39;_blank&#39;&gt;here&lt;/a&gt;. | [optional]
**callback_handle** | **string** | An arbitrary string that finAPI will include into the notifications that it sends based on this rule and that you can use to identify the notification in your application. For instance, you could include the identifier of the user that you create this rule for.&lt;br/&gt;&lt;br/&gt;Note that for this parameter, you can pass the symbols &#39;/&#39;, &#39;&#x3D;&#39;, &#39;%&#39; and &#39;\&quot;&#39; in addition to the symbols that are generally allowed in finAPI (see &lt;a href&#x3D;&#39;https://documentation.finapi.io/access/Allowed-Characters.2764767279.html&#39; target&#x3D;&#39;_blank&#39;&gt;Allowed Characters&lt;/a&gt;). This was done to enable you to set Base64 encoded strings and JSON structures for the callback handle. | [optional]
**include_details** | **bool** | Whether the notification messages that will be sent based on this rule should contain encrypted detailed data or not. Default value is &#39;false&#39;. | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
