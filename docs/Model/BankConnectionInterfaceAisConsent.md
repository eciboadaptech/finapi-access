# # BankConnectionInterfaceAisConsent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | [**\OpenAPI\Client\Model\BankConsentStatus**](BankConsentStatus.md) |  |
**expires_at** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;Expiration time of the consent. | [optional]
**supports_import_new_accounts** | **bool** | Whether this consent supports the download of accounts that weren&#39;t downloaded at the time when the consent was issued. If this field is false, then you will have to delete this consent before you can update the bank connection with &#39;importNewAccounts&#39; &#x3D; true (otherwise, the update will result in an error). Please note that the user will have to be involved in the process of issuing a new consent. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
