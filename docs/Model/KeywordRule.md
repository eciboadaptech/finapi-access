# # KeywordRule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Rule identifier |
**category** | [**\OpenAPI\Client\Model\IbanRuleCategory**](IbanRuleCategory.md) |  |
**direction** | [**\OpenAPI\Client\Model\TransactionDirection**](TransactionDirection.md) |  |
**creation_date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Timestamp of when the rule was created. |
**keywords** | **string[]** | Set of keywords that this rule defines. |
**keywords_language** | [**\OpenAPI\Client\Model\Language**](Language.md) |  |
**all_keywords_must_match** | **bool** | This field is only relevant if the rule contains multiple keywords. If set to &#39;true&#39; it means that all keywords have to be found in a transaction to apply the given category. If set to &#39;false&#39;, then even a single matching keyword in a transaction can trigger this rule. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
