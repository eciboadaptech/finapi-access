# # DailyBalance

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | **\DateTime** | &lt;strong&gt;Format:&lt;/strong&gt; &#39;YYYY-MM-DD&#39;&lt;br/&gt;Date. |
**balance** | **float** | Calculated balance at the end of day, across all regarded accounts. Note that the balance may not always add up to the income/spending of the day. This happens when a bank reports a balance that includes transactions which the bank didn&#39;t (yet) deliver. In any case, it is recommended to rely on the balance rather than on calculations based on the income/spending. |
**income** | **float** | The sum of income of the given day, based on the &#39;transactions&#39;, across all regarded accounts. |
**spending** | **float** | The sum of spending of the given day, based on the &#39;transactions&#39;, across all regarded accounts. Note that this is an absolute (i.e. positive) value. |
**internal_adjusting_entries** | **float** | Sometimes finAPI may detect deviations between the bank reported account balance and the set of transactions received from the bank. This is an expected behaviour when an account has not been updated for a while, as banks provide only a limited history of transactions. In such cases, finAPI adds an adjusting entry (see the field Transaction.isAdjustingEntry), which will be contained in the &#39;transactions&#39; list, just as any other transaction.&lt;br/&gt;&lt;br/&gt;However, if an account was regularly updated and gaps in the transaction history are not expected, then finAPI will fix such deviations by adding an internal adjusting entry. These internal entries are not visible in the API and will not be contained in the &#39;transactions&#39; list, and thus also not regarded for the calculations of &#39;income&#39; and &#39;spending&#39;. They are however regarded for the calculation of the &#39;balance&#39;.&lt;br/&gt;&lt;br/&gt;As long as you don&#39;t do your own balance calculations, you do not need to regard this field here; The &#39;balance&#39; will always be correct. But if you do your own calculations, then you should not only regard the &#39;income&#39; and &#39;spending&#39;, but this field as well.&lt;br/&gt;&lt;br/&gt;Note that unlike the &#39;income&#39; and &#39;spending&#39;, this field can have a positive or negative value. |
**transactions** | **int[]** | Identifiers of the transactions for the given day |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
