# # DailyBalanceList

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**latest_common_balance_timestamp** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;T&#39;HH:MM:SS.SSSXXX&#39; (RFC 3339, section 5.6)&lt;br/&gt;The latestCommonBalanceTimestamp is the latest timestamp at which all regarded  accounts have been up to date. Only balances with their date being smaller than the latestCommonBalanceTimestamp are reliable. &lt;br/&gt;Example: A user has two accounts: A (last update today, so balance from today) and B (last update yesterday, so balance from yesterday). The service /accounts/dailyBalances will return a balance for yesterday and for today, with the info latestCommonBalanceTimestamp&#x3D;yesterday. Since account B might have received transactions this morning, today&#39;s balance might be wrong. So either make sure that all regarded accounts are up to date before calling this service, or use the results carefully in combination with the latestCommonBalanceTimestamp.&lt;br/&gt;&lt;br/&gt;NOTE:&lt;br/&gt;The returned balances are completely unreliable if the &#39;latestCommonBalanceTimestamp&#39; is null. This can occur if the balance download failed for any account or the &#39;skipBalancesDownload&#39; flag was set to true for the bank connection import or a subsequent update. | [optional]
**daily_balances** | [**\OpenAPI\Client\Model\DailyBalance[]**](DailyBalance.md) | List of daily balances for the requested period and account(s)&lt;br/&gt; &lt;strong&gt;Type:&lt;/strong&gt; DailyBalance |
**paging** | [**\OpenAPI\Client\Model\DailyBalanceListPaging**](DailyBalanceListPaging.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
