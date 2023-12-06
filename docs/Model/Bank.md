# # Bank

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** | Bank identifier |
**name** | **string** | Name of bank |
**bic** | **string** | BIC of bank | [optional]
**blz** | **string** | BLZ of bank. Please do NOT use this field to identify a bank, since there can be multiple banks with the same BLZ. If you need to identify a bank, refer to the &lt;code&gt;id&lt;/code&gt; field instead. |
**location** | **string** | Bank location (two-letter country code; ISO 3166 ALPHA-2). Note that when this field is not set, it means that this bank depicts an international institute which is not bound to any specific country. | [optional]
**city** | **string** | City that this bank is located in. Note that this field may not be set for some banks. | [optional]
**is_test_bank** | **bool** | If true, then this bank does not depict a real bank, but rather a testing endpoint provided by a bank or by finAPI. You probably want to regard these banks only during the development of your application, but not in production. You can filter out these banks in production by making sure that the &#39;isTestBank&#39; parameter is always set to &#39;false&#39; whenever your application is calling the &#39;Get and search all banks&#39; service. |
**popularity** | **int** | Popularity of this bank with your users (mandator-wide, i.e. across all of your clients). The value equals the number of bank connections that are currently imported for this bank across all of your users (which means it is a constantly adjusting value). You can use this field for statistical evaluation, and also for ordering bank search results (see service &#39;Get and search all banks&#39;). |
**interfaces** | [**\OpenAPI\Client\Model\BankInterface[]**](BankInterface.md) | Set of interfaces that exist for the bank.&lt;br/&gt;&lt;br/&gt;Note:&lt;br/&gt;&amp;bull; If the set is empty, then the bank is not supported.&lt;br/&gt;&amp;bull; Even if an interface is listed, it might not be usable at the moment. Please always refer to the fields &#39;BankInterface.isAisSupported&#39; / &#39;BankInterface.isPisSupported&#39; before you attempt to use an interface.&lt;br/&gt;&amp;bull; The WEB_SCRAPER interface might be disabled for your client (see GET /clientConfiguration). When this is the case, then finAPI will not use the web scraper for data download, and if the web scraper is the only supported interface of this bank, then finAPI will not allow to download any data for this bank at all (for details, see POST /bankConnections/import and POST /bankConnections/update). Also, you will not be able to do payments via the WEB_SCRAPER interface, if web scraping is disabled for your client.&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; BankInterface |
**bank_group** | [**\OpenAPI\Client\Model\BankBankGroup**](BankBankGroup.md) |  | [optional]
**is_beta** | **bool** | Whether this bank is in beta phase. For more details, please refer to the field ClientConfiguration.betaBanksEnabled. |
**logo** | [**\OpenAPI\Client\Model\BankLogo**](BankLogo.md) |  | [optional]
**icon** | [**\OpenAPI\Client\Model\BankIcon**](BankIcon.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
