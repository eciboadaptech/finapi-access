# # KeywordRuleParams

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**category_id** | **int** | ID of the category that this rule should assign to the matching transactions |
**direction** | [**\OpenAPI\Client\Model\CategorizationRuleDirection**](CategorizationRuleDirection.md) |  |
**keywords** | **string[]** | Set of keywords for the rule (Keywords are regarded case-insensitive). |
**keywords_language** | [**\OpenAPI\Client\Model\Language**](Language.md) |  | [optional]
**all_keywords_must_match** | **bool** | This field is only relevant if you pass multiple keywords. If set to &#39;true&#39;, it means that all keywords have to be found in a transaction to apply the given category. If set to &#39;false&#39;, then even a single matching keyword in a transaction can trigger this rule. Default value is &#39;false&#39;. | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
