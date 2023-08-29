## t(:understandingratelimits)
t(:rate_para_understanding_v3)

```
// Response header

Content-Type: application/json; charset=utf-8
Content-Length: 957
MF-ACCESS-Limit: 5
MF-ACCESS-Limit-Status: 4
MF-ACCESS-Limit-Reset-Timestamp: 1665397625986
```

* `MF-ACCESS-Limit-Status` - t(:rate_text_limitStatus_understanding)
* `MF-ACCESS-Limit` - t(:rate_text_limit_understanding)
* `MF-ACCESS-Limit-Reset-Timestamp` - t(:rate_text_limitReset)

### t(:perendpoint)
<table class="custom_table">
  <tr>
    <th>t(:row_comment_rate_limit)</th>
    <th>t(:row_comment_path)</th>
  </tr>
  <tr>
    <td rowspan="1">5 requests/second</td>
    <td>All private endpoints</td>
  </tr>
  <tr>
    <td rowspan="1">1 requests/2 second</td>
    <td>batch requests</td>
  </tr>
</table>
t(:ratelimitUsdc)
