# t(:accountdata)
t(:account_para)

## t(:trade)
### t(:dv_placeOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.mufex.finance/private/v1/trade/create' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: f02a18137c25c40d64b2c474f575c01a62ba076124946d38619238e19c86a2f2' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658884339826' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol": "ETHUSDT",
    "side": "Sell",
    "positionIdx": 2,
    "orderType": "Limit",
    "qty": "0.5",
    "price": "1450",
    "triggerDirection": 2,
    "triggerPrice": "1500",
    "triggerBy": "MarkPrice",
    "timeInForce": "GoodTillCancel",
    "orderLinkId": "a003",
    "takeProfit": "1100",
    "stopLoss": "1700",
    "reduce_only": false,
    "closeOnTrigger": false,
    "pzLinkId": "49e5e569-dc26-4263-8feb-77f543637002"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code":0,
        "message":"OK",
        "data": {
        "orderId":"a09a43f1-7a65-4255-8758-034103447a4e",
        "orderLinkId":""
    },
    "ext_info":null,
        "time":1658850321861
}
```

t(:contract_order_para)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCreate>/private/v1/trade/create</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCreate"><img src="/images/copy_to_clipboard.png" height=zh5 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol)   |
|side |<b>true</b> |string | Buy| Sell :Closing a position is done by opening a reverse order|
|positionIdx |true |integer |t(:row_comment_position_idx_create_order_v3)  |
|t(:contract_param_orderType) |<b>true</b> |string |t(:row_comment_activeOrderType)   |
|qty |<b>true</b> |string |t(:contract_comment_qty) |
|price |false |string |t(:contract_comment_price) |
|triggerDirection |false |integer |t(:contract_comment_triggerDirection) |
|triggerPrice |false |string |t(:contract_comment_triggerPrice) |
|<a href="#trigger-price-type-triggerby">triggerBy</a> |false |string |t(:row_comment_linear_triggerBy) |
|tpTriggerBy |false |string |t(:account_row_comment_tp_trigger_by) |
|slTriggerBy |false |string |t(:account_row_comment_sl_trigger_by) |
|t(:row_parameter_timeInForce) |<b>true</b> |string |t(:row_comment_timeInForce) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|takeProfit |false |string |t(:row_comment_takeProfit) |
|stopLoss |false |string |t(:row_comment_stopLoss) |
|reduceOnly |false |bool |t(:linear_row_comment_reduceOnly) |
|closeOnTrigger |false |bool |t(:linear_row_comment_closeOnTrigger)|
|pzLinkId |false |string |t(:row_comment_pzLinkId) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
| orderId |string |t(:row_comment_order_id) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |

### t(:contract_getOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/trade/orders?symbol=BTCUSDT&orderStatus=Filled' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: 61df2c2de39cfce40fe334e503de4a61e26a95aebec690b9b482e4feb31cb088' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658899014497' \
--header 'MF-ACCESS-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
    "message": "OK",
    "data":  {
        "list": [
            {
                "symbol": "BTCUSDT",
                "side": "Buy",
                "orderType": "Market",
                "price": "0.3431",
                "qty": "65",
                "reduceOnly": true,
                "timeInForce": "ImmediateOrCancel",
                "orderStatus": "Filled",
                "leavesQty": "0",
                "leavesValue": "0",
                "cumExecQty": "65",
                "cumExecValue": "21.3265",
                "cumExecFee": "0.0127959",
                "lastPriceOnCreated": "0.0000",
                "rejectReason": "EC_NoError",
                "orderLinkId": "",
                "createdTime": "1657526321499",
                "updatedTime": "1657526321504",
                "orderId": "ac0a8134-acb3-4ee1-a2d4-41891c9c46d7",
                "stopOrderType": "UNKNOWN",
                "takeProfit": "0.0000",
                "stopLoss": "0.0000",
                "tpTriggerBy": "UNKNOWN",
                "slTriggerBy": "UNKNOWN",
                "triggerPrice": "0.0000",
                "closeOnTrigger": true,
                "triggerDirection": 0,
                "positionIdx": 2
        ],
        "nextPageCursor": "K0crQkZRL0MyQVpiN0tVSDFTS0RlMk9DemNCWHZaRHp3aFZ4Y1Yza2MyWT0="
    },
    "ext_info": {},
    "time": 1658899014975
}
```

t(:contract_para_getOrder)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oaoList>/private/v1/trade/orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:account_row_comment_orderId) |
|orderLinkId |false |string |t(:row_comment_orderLinkId) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|<a href="#order-status-orderstatus-stoporderstatus">orderStatus</a> |false |string |t(:orderStatus_v3) |
|orderFilter |false |string |t(:row_comment_orderFilter_v3) |
|limit |false |integer |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> symbol |string |t(:row_comment_symbol) |
|list> side |string |t(:row_comment_side) |
|list> orderType |string |t(:row_comment_order_type) |
|list> price |string |t(:row_comment_resp_price) |
|list> qty |string |t(:contract_comment_qty) |
|list> reduceOnly |bool |t(:linear_resp_field_reduce_only)  |
|list> timeInForce |string |t(:row_comment_timeInForce)  |
|list> orderStatus |string |t(:row_comment_orderStatus)  |
|list> leavesQty |string |t(:row_comment_leaves_qty)  |
|list> leavesValue |string |t(:row_comment_leaves_value)  |
|list> cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|list> cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|list> cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|list> lastPriceOnCreated |string |t(:row_comment_last_exec_price)  |
|list> rejectReason |string |t(:row_comment_query_rejectReason_v3) |
|list> createdTime |string |t(:row_comment_created_at)  |
|list> updatedTime |string |t(:row_comment_updated_at)  |
|list> orderLinkId |string |t(:row_comment_orderLinkId)  |
|list> orderId |string |t(:account_row_comment_orderId) |
|list> stopOrderType |string |t(:row_comment_stopOrderType) |
|list> triggerDirection |integer |t(:contract_comment_triggerDirection) |
|list> closeOnTrigger |bool |t(:row_response_close_on_trigger)  |
|list> takeProfit |string |t(:row_comment_take_profit)  |
|list> stopLoss |string |t(:row_comment_stop_loss)  |
|list> tpTriggerBy |string |t(:contract_comment_tpTriggerBy) |
|list> slTriggerBy |string |t(:contract_comment_slTriggerBy) |
|list> triggerBy |string |The price type of trigger price |
|list> triggerPrice |string |t(:contract_comment_getOrderTriggerPrice) |
|list> positionIdx |integer |t(:row_comment_position_idx) |
|nextPageCursor |string |t(:contract_comment_nextPageCursor) |


### t(:contract_cancelOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.mufex.finance/private/v1/trade/cancel' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: c9f2c118e40040fc3a12c9400816a26e475ce2f7995248a3625d92be3454b9f1' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658900794413' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
  "symbol": "XRPUSDT",
  "orderLinkId": null,
  "orderId": "4030430d-1dba-4134-ac77-3d81c14aaa00"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code":0,
    "message":"OK",
    "data": {
      "orderId": "4030430d-1dba-4134-ac77-3d81c14aaa00",
      "orderLinkId": ""
  },
  "ext_info":null,
    "time":1658850321861
}
```

t(:contract_para_cancelOrder)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=vpoCancel>/private/v1/trade/cancel</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpoCancel"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|orderId |false |string |t(:row_comment_orderId_v3_post) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_v3_post) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|orderId |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:misc_row_comment_orderLinkIdNotOrderId) |


### t(:contract_replaceOrder)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.mufex.finance/private/v1/trade/replace' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: 78c358649d431bb30dfc35e5a3cd99128b5f23faf04c15765b3d894f2930e8f5' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658902610018' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "orderId":"db8b74b3-72d3-4264-bf3f-52d39b41956e",
    "orderLinkId": null,
    "qty": "15",
    "price": "0.4"
}'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "orderId": "db8b74b3-72d3-4264-bf3f-52d39b41956e",
            "orderLinkId": "x002"
    },
    "ext_info": {},
    "time": 1658902610749
}
```

t(:contract_para_replaceOrder)

<aside class="notice">
t(:account_aside_replaceActive)
</aside>

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=oaoReplace>/private/v1/trade/replace</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oaoReplace"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:row_comment_orderId_replace) |
|orderLinkId |false |string |t(:row_comment_orderLinkId_replace) |
|symbol |<b>true</b> |string |t(:row_comment_symbol) |
|qty |false |string |t(:row_comment_pRQty) |
|price |false |string |t(:row_comment_pRPrice) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|order_id |string |t(:account_row_comment_orderId) |
|orderLinkId |string |t(:row_comment_orderLinkId)  |


### t(:contract_getOpenOrder)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/trade/activity-orders?symbol=XRPUSDT' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: e3a1e4b88dfc2730c987fb3253dd3e09bc05cf68ae4d9d9d71a8235c44cb1f02' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658902846749' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json'
```

```python--pybit

```

> t(:codequote_responseExample)

```json
{
  "code": 0,
  "message": "OK",
  "data":  {
    "list": [
      {
        "symbol": "XRPUSDT",
        "orderId": "db8b74b3-72d3-4264-bf3f-52d39b41956e",
        "side": "Sell",
        "orderType": "Limit",
        "stopOrderType": "Stop",
        "price": "0.4000",
        "qty": "15",
        "timeInForce": "GoodTillCancel",
        "orderStatus": "UnTriggered",
        "triggerPrice": "0.1000",
        "orderLinkId": "x002",
        "createdTime": "1658901865082",
        "updatedTime": "1658902610748",
        "takeProfit": "0.2000",
        "stopLoss": "1.6000",
        "tpTriggerBy": "UNKNOWN",
        "slTriggerBy": "UNKNOWN",
        "triggerBy": "MarkPrice",
        "reduceOnly": false,
        "leavesQty": "15",
        "leavesValue": "6",
        "cumExecQty": "0",
        "cumExecValue": "0",
        "cumExecFee": "0",
        "triggerDirection": 2
      }
    ],
    "nextPageCursor": ""
  },
  "ext_info": {},
  "time": 1658902847238
}
```


t(:contract_para_getRealtimeOrder)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpOrder>/private/v1/trade/activity-orders</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpOrder"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |false |string |t(:contract_comment_realtimeOrderSymbol) |
|orderId |false |string | t(:misc_row_comment_orderIdNotOrderLinkId)|
|orderLinkId |false |string |t(:misc_row_comment_orderLinkIdNotOrderId) |
|<a href="#order-filter-orderfilter">orderFilter</a> |false |string | t(:row_comment_orderFilter_v3)|
|limit |false |number |t(:row_comment_limit) |
|cursor |false |string |t(:row_comment_resp_cursor)   |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|> symbol |string |t(:row_comment_symbol)    |
|> orderId |string |t(:row_comment_order_id) |
|> side |string |t(:row_comment_side)  |
|> orderType |string |t(:row_comment_order_type)  |
|> triggerDirection |integer |t(:contract_comment_triggerDirection)  |
|> price |string |t(:row_comment_resp_price)  |
|> qty |string |t(:contract_comment_qty)  |
|> timeInForce |string |t(:row_comment_timeInForce)  |
|> orderStatus |string |t(:row_comment_orderStatus)  |
|> triggerPrice |string |t(:contract_comment_triggerPrice)  |
|> triggerBy |string |t(:row_comment_linear_triggerBy) |
|> tpTriggerBy |string |t(:account_row_comment_tp_trigger_by) |
|> slTriggerBy |string |t(:account_row_comment_sl_trigger_by) |
|> orderLinkId |string |t(:row_comment_orderLinkId)  |
|> createdTime |string |t(:row_comment_created_at)  |
|> updatedTime |string |t(:row_comment_updated_at)  |
|> takeProfit |string |t(:row_comment_take_profit)  |
|> stopLoss |string |t(:row_comment_stop_loss)  |
|> reduce_only |bool |t(:linear_resp_field_reduce_only)  |
|> cumExecQty |string |t(:linear_resp_field_cum_exec_qty)  |
|> cumExecValue |string |t(:linear_resp_field_cum_exec_value)  |
|> cumExecFee |string |t(:linear_resp_field_cum_exec_fee)  |
|> leavesQty |string |t(:row_comment_leaves_qty)  |
|> leavesValue |string |t(:row_comment_leaves_value)  |
|nextPageCursor |string |t(:row_comment_query_nextPageCursor_v3)  |

### t(:usertraderecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/trade/fills?symbol=BTCUSDT' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: a7358fb068bf66570e7ecf063e39a6dbd11f1d5572ba79a63d5996221d864585' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658911518042' \
--header 'MF-ACCESS-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "list": [
            {
                "symbol": "BTCUSDT",
                "execFee": "0.00293025",
                "execId": "16bff97b-0e04-4303-82b5-1b1134f15695",
                "execPrice": "0.00",
                "execQty": "0.001",
                "execType": "Funding",
                "execValue": "29.30248",
                "feeRate": "0.0001",
                "lastLiquidityInd": "UNKNOWN",
                "leavesQty": "0.000",
                "orderId": "1690588800-BTCUSDT-139688-Buy",
                "orderLinkId": "",
                "orderPrice": "0.00",
                "orderQty": "0.000",
                "orderType": "UNKNOWN",
                "stopOrderType": "UNKNOWN",
                "side": "Buy",
                "execTime": "1690588800000",
                "closedSize": "0.000",
                "crossSeq": "41019846"
            },
            {
                "symbol": "BTCUSDT",
                "execFee": "0.00293787",
                "execId": "d9439111-d9ee-4cf3-90e1-85e8f148b6a3",
                "execPrice": "0.00",
                "execQty": "0.001",
                "execType": "Funding",
                "execValue": "29.3787",
                "feeRate": "0.0001",
                "lastLiquidityInd": "UNKNOWN",
                "leavesQty": "0.000",
                "orderId": "1690560000-BTCUSDT-139688-Buy",
                "orderLinkId": "",
                "orderPrice": "0.00",
                "orderQty": "0.000",
                "orderType": "UNKNOWN",
                "stopOrderType": "UNKNOWN",
                "side": "Buy",
                "execTime": "1690560000000",
                "closedSize": "0.000",
                "crossSeq": "40849025"
            }
        ],
            "nextPageCursor": ""
    },
    "ext_info": {},
    "time": 1658911518442
}
```

t(:linear_private_trade_records)

<aside class="notice">
t(:wallet_aside_tradeRecords)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpeList>/private/v1/trade/fills</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpeList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|orderId |false |string |t(:contract_comment_orderId) |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|startTime |false |number |t(:contract_comment_startTime) |
|endTime |false |number |t(:contract_comment_endTime) |
|<a href="#exec-type-exectype">execType</a> |false |string |t(:linear_exec_type) |
|limit |false |integer |t(:linear_row_comment_limit_50_200) |
|cursor |false |string |t(:row_comment_resp_cursor)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> t(:row_parameter_symbol) |string |t(:row_comment_symbol)  |
|list> execFee |string |t(:row_comment_exec_fee)    |
|list> execId |string |t(:row_comment_exec_id)  |
|list> execPrice |string |t(:row_comment_exec_price)    |
|list> execQty |string |t(:row_comment_exec_qty)  |
|list> execType |string |t(:row_comment_exec_type) |
|list> execValue |string |t(:row_comment_exec_value)  |
|list> feeRate |string |t(:row_comment_fee_rate)  |
|list> <a href="#liquidity-type-lastliquidityind">lastLiquidityInd</a> |string |t(:row_comment_last_liquidity_ind) |
|list> leavesQty |string |t(:row_comment_leaves_qty)  |
|list> orderId |string |t(:row_comment_order_id)  |
|list> orderLinkId |string |t(:row_comment_orderLinkId)  |
|list> orderPrice |string |t(:row_comment_order_price)  |
|list> orderQty |string |t(:row_comment_order_qty)  |
|list> orderType |string |t(:row_comment_order_type)  |
|list> <a href="#stop-order-type-stopordertype">stopOrderType</a> |string |t(:row_comment_stopOrderType)  |
|list> t(:row_parameter_side) |string |t(:row_comment_side)  |
|list> execTime |string |t(:row_comment_query_execTime_v3)  |
|list> closedSize |string |t(:row_comment_closedSize_v3)  |
|list> crossSeq| int64| cross seq|
|nextPageCursor |string |t(:contract_comment_nextPageCursor)  |


## t(:account)
### t(:dv_myposition)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/account/positions?symbol=ETHUSDT' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: b0818cb2f91264ffd712db0c8f8648041b2c5eed643200aa63e4141c7aa12500' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658904877491' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw ''
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "list": [
            {
                "positionIdx": 0,
                "riskId": 11,
                "symbol": "ETHUSDT",
                "side": "None",
                "size": "0.00",
                "positionValue": "0",
                "entryPrice": "0",
                "tradeMode": 1,
                "autoAddMargin": 0,
                "leverage": "10",
                "positionBalance": "0",
                "liqPrice": "0.00",
                "bustPrice": "0.00",
                "takeProfit": "0.00",
                "stopLoss": "0.00",
                "trailingStop": "0.00",
                "unrealisedPnl": "0",
                "createdTime": "1659943372099",
                "updatedTime": "1669470547908",
                "tpSlMode": "Full",
                "riskLimitValue": "900000",
                "activePrice": "0.00",
                "markPrice": "1205.02",
                "cumRealisedPnl": "0.00",
                "positionMM": "",
                "positionIM": "",
                "positionStatus": "Normal",
                "sessionAvgPrice": "0.00",
                "pzLinkId": "",
                "isSeparatePz": false
                
            }
        ],
            "separateList": []
            "category": "linear",
            "nextPageCursor": ""
    },
    "ext_info": {},
    "time": 1670836410404
}

{
    "code": 0,
    "message": "OK",
    "data": {
    "list": [],
        "category": "",
        "nextPageCursor": "",
        "separateList": [
        {
            "positionIdx": 1,
            "riskId": "0",
            "symbol": "BTCUSDT",
            "side": "Buy",
            "size": "0.001",
            "positionValue": "57.6742",
            "entryPrice": "57674.2",
            "tradeMode": 0,
            "autoAddMargin": 0,
            "leverage": "10",
            "positionBalance": "5.76742",
            "liqPrice": "0.1",
            "bustPrice": "0.1",
            "takeProfit": "0.0",
            "stopLoss": "0.0",
            "trailingStop": "0.0",
            "unrealisedPnl": "-0.9374",
            "createdTime": "1726017294861",
            "updatedTime": "1726026707029",
            "tpSlMode": "Partial",
            "riskLimitValue": "0",
            "activePrice": "0.0",
            "markPrice": "56736.8",
            "cumRealisedPnl": "-0.03460452",
            "positionMm": "",
            "positionIm": "",
            "positionStatus": "Normal",
            "sessionAvgPrice": "0.0",
            "pzLinkId": "3c582eef-33e9-41b4-98c5-37278c735576",
            "isSeparatePz": true
        }
    ]
},
    "ext_info": {},
    "time": 1726026707032
}
```

t(:contract_para_position)

<aside class="notice">
t(:account_aside_queryPosition)
</aside>

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pList>/private/v1/account/positions</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pList"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |false |string |t(:contract_comment_realtimeOrderSymbol)    |
|settleCoin |false |string |t(:contract_comment_positionSettleCoin)    |
|limit |false |integer |t(:contract_position_limit)    |
|cursor |false |string |t(:row_comment_resp_cursor)    |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|positionIdx |integer |t(:row_comment_position_idx)  |
|riskId  |integer |t(:contract_comment_riskId) |
|riskLimitValue | string | t(:contract_position_riskLimitValue) |
|t(:row_parameter_symbol)|string |t(:row_comment_symbol)    |
|t(:row_parameter_side) |string |t(:row_comment_side)  |
|size |string |t(:row_comment_position_size)  |
|positionValue |string |t(:row_comment_position_value)  |
|entryPrice |string |t(:linear_resp_field_entry_price)  |
|markPrice |string |t(:row_comment_updated_at)  |
|tradeMode |integer |t(:contract_comment_tradeMode) |
|autoAddMargin |integer |t(:row_comment_auto_add_margin)  |
|leverage |string |t(:resp_field_leverage)  |
|positionBalance |string |t(:contract_comment_positionBalance)  |
|liqPrice |string |t(:linear_resp_field_liq_price)  |
|bustPrice |string |t(:linear_resp_field_bust_price)  |
|positionStatus |string |t(:row_comment_updated_at)  |
|sessionAvgPrice |string |t(:row_comment_query_sessionAvgPrice_v3)  |
|takeProfit |string |t(:row_comment_take_profit)  |
|stopLoss |string |t(:row_comment_stop_loss)  |
|trailingStop |string |t(:row_comment_trailing_stop)  |
|unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|<a href="#tp-sl-mode-tpslmode">tpSLMode</a> |string |t(:row_comment_tp_sl_mode)  |
|activePrice | string | t(:account_row_comment_activePrice_v3) |
|positionIM |string |t(:row_comment_query_positionIM_v3)  |
|positionMM |string |t(:row_comment_query_positionMM_v3)  |
|cumRealisedPnl |string |t(:row_comment_query_cumRealisedPnl_v3)  |
|pzLinkId |false |string |t(:row_comment_pzLinkId) |
|createdTime |string |t(:row_comment_created_at)  |
|updatedTime |string |t(:row_comment_updated_at)  |
|nextPageCursor | string | t(:contract_comment_nextPageCursor) |


### t(:dv_marginswitch)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.mufex.finance/private/v1/account/set-isolated' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: f178bda84f8a3fa971338b7424cce2204824c0114f196650b2516962371e3902' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658908531694' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "tradeMode": 1,
    "buyLeverage": "5",
    "sellLeverage": "5"
}'
```
```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {},
    "ext_info": {},
    "time": 1658908532580
}
```


t(:contract_para_switchIsolated)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSwitchIsolated>/private/v1/account/set-isolated</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSwitchIsolated"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|tradeMode |<b>true</b> |integer |t(:contract_comment_tradeMode)  |
|buyLeverage |<b>false</b> |string |t(:contract_comment_buyLeverage)  |
|sellLeverage |<b>false</b> |string |t(:contract_comment_sellLeverage)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:linear_account_para_switchSeparatePositionMod)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.mufex.finance/private/v1/account/switch-separate-position' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: f178bda84f8a3fa971338b7424cce2204824c0114f196650b2516962371e3902' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658908531694' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "coin": "USDT",
    "isSeparatePz": true
}'
```
```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
        "code": 0, 
        "message": "Success",
        "data":  {},
        "ext_info": {},
        "time": 1658908532580
}
```

t(:contract_para_switchSeparatePositionMod)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSwitchSeparatePositionMod>/private/v1/account/switch-separate-position</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|coin |<b>true</b> |string |t(:contract_comment_coin)  |
|isSeparatePz |<b>true</b> |bool |t(:contract_comment_isSeparatePz)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |


### t(:linear_account_para_setLeverage)
> t(:codequote_curlExample)

```console
curl --location --request POST 'https://api.mufex.finance/private/v1/account/set-leverage' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: f178bda84f8a3fa971338b7424cce2204824c0114f196650b2516962371e3902' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658908531694' \
--header 'MF-ACCESS-RECV-WINDOW: 5000' \
--header 'Content-Type: application/json' \
--data-raw '{
    "symbol":"XRPUSDT",
    "buyLeverage": "5",
    "sellLeverage": "5"
}'
```
```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {},
    "ext_info": {},
    "time": 1658908532580
}
```

t(:contract_para_setLeverage)

<p class="fake_header">t(:httprequest)</p>
POST
<code><span id=pSetLeverage>/private/v1/account/set-leverage</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pSetLeverage"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol)    |
|buyLeverage |<b>true</b> |string |t(:contract_comment_buyLeverage)  |
|sellLeverage |<b>true</b> |string |t(:contract_comment_sellLeverage)  |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |

### t(:dv_closedprofitandloss)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/account/closed-pnl?symbol=XRPUSDT&startTime=1658764800000&endTime=1658937600000' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: eb16a696924a92a3a47d769caf44d7373eca9ed6a644384ff6e8cd729ee9f7b1' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658914264517' \
--header 'MF-ACCESS-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "list": [
            {
                "symbol": "XRPUSDT",
                "orderId": "3834da81-2b9c-4f5b-a558-05091f26deda",
                "side": "Buy",
                "qty": "50",
                "orderPrice": "0.3541",
                "orderType": "Market",
                "execType": "Trade",
                "closedSize": "50",
                "cumEntryValue": "16.68",
                "avgEntryPrice": "0.3336",
                "cumExitValue": "16.865",
                "avgExitPrice": "0.3373",
                "closedPnl": "-0.2034435",
                "fillCount": "1",
                "leverage": "10",
                "createdAt": "1658914152212"
            }
        ],
            "nextPageCursor": "R21aYkRjQ0haRmcxeFJBanZNYm1Db01RWWdyV3YzZmdkUVNXUmtXdGpMMD0="
    },
    "ext_info": {},
    "time": 1658914264892
}
```

t(:linear_private_closed_pnl_records)

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=pltcLpnl>/private/v1/account/closed-pnl</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#pltcLpnl"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|t(:row_parameter_symbol) |<b>true</b> |string |t(:row_comment_symbol) |
|startTime |false |number |t(:row_comment_startTime) |
|endTime |false |number |t(:row_comment_endTime) |
|limit |false |integer |t(:linear_row_comment_limit_50_200) |
|cursor |false |string |t(:row_comment_resp_cursor)    |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> orderId |string |t(:row_response_closedPnlOrderId)  |
|list> t(:row_parameter_symbol) |string |t(:row_comment_symbol)    |
|list> t(:row_parameter_side) |string |t(:row_response_closedPnlSide)  |
|list> t(:row_parameter_quantity) |string |t(:row_comment_order_qty)  |
|list> orderPrice |string |t(:row_comment_order_price)  |
|list> orderType |string |t(:row_comment_order_type)  |
|list> execType |string |t(:row_comment_exec_type)  |
|list> closedSize |string |t(:linear_resp_field_closed_size)  |
|list> cumEntryValue |string |t(:linear_resp_field_cum_entry_value)    |
|list> avgEntryPrice |string |t(:linear_resp_field_avg_entry_price)    |
|list> cumExitValue |string |t(:linear_resp_field_cum_exit_value)    |
|list> avgExitPrice |string |t(:linear_resp_field_avg_exit_price)    |
|list> closedPnl |string |t(:linear_resp_field_closed_pnl)    |
|list> fillCount |string |t(:linear_resp_field_fill_count)    |
|list> leverage |string |t(:resp_field_leverage)  |
|list> createdAt |string |t(:row_comment_created_at)  |
|nextPageCursor |string |t(:contract_comment_nextPageCursor)  |





### t(:balance)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/account/balance?coin=BTC' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: f8f516355e0c59b28d429b13b4ea6a350d02f9c96e2f9fd1be235863e8c1834c' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658736635286' \
--header 'MF-ACCESS-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "list": [
            {
                "coin": "BTC",
                "equity": "0.80319649",
                "walletBalance": "0.80319649",
                "positionMargin": "0",
                "availableBalance": "0.80319649",
                "orderMargin": "0",
                "occClosingFee": "0",
                "occFundingFee": "0",
                "unrealisedPnl": "0",
                "cumRealisedPnl": "0.00120039",
                "givenCash": "0",
                "serviceCash": "0"
            }
        ]
    },
    "ext_info": {},
    "time": 1658736635763
}
```

t(:wallet_para_walletBalance)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=vpwBalance>/private/v1/account/balance</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#vpwBalance"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:contract_accountCoin) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> coin |string |t(:contract_accountCoin_resp)  |
|list> equity |string |t(:row_comment_equity)  |
|list> walletBalance |string |t(:row_comment_wallet_balance)  |
|list> positionMargin |string |t(:row_comment_position_margin)  |
|list> availableBalance |string |t(:row_comment_http_available_balance)  |
|list> orderMargin|string |t(:row_comment_order_margin)    |
|list> occClosingFee |string |t(:row_comment_occ_closing_fee)  |
|list> occFundingFee |string |t(:row_comment_occ_funding_fee)  |
|list> unrealisedPnl |string |t(:row_comment_unrealised_pnl)  |
|list> cumRealisedPnl|string |t(:row_comment_cum_realised_pnl)  |
|list> givenCash |string |t(:row_response_comment_given_cash)  |
|list> serviceCash |string |t(:row_response_comment_service_cash)  |


### t(:tradingFeeRate)
t(:contract_tradingFeeRate_para)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/account/trade-fee?symbol=ETHUSDT' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: e65aad8dd5459774ad21aaca77420947332fdbfe433bef959c6507ce2379999f' \
--header 'MF-ACCESS-API-KEY: XXXXXXXXXXXX' \
--header 'MF-ACCESS-TIMESTAMP: 1658739026859' \
--header 'MF-ACCESS-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "list": [
            {
                "symbol": "ETHUSDT",
                "takerFeeRate": "0.0009",
                "makerFeeRate": "0.0003"
            }
        ]
    },
    "ext_info": {},
    "time": 1658739027301
}
```

<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=tradingFeeRate>/private/v1/account/trade-fee</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#tradingFeeRate"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|symbol |false |string |t(:row_comment_symbol) |

<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> symbol |string |t(:row_comment_symbol)  |
|list> takerFeeRate |string |t(:contract_accountTakerFeeRate)  |
|list> makerFeeRate |string |t(:contract_accountMakerFeeRate)  |


### t(:dv_walletrecords)
> t(:codequote_curlExample)

```console
curl --location --request GET 'https://api.mufex.finance/private/v1/account/bills?coin=USDT&walletFundType=RealisedPNL&limit=1' \
--header 'MF-ACCESS-SIGN-TYPE: 2' \
--header 'MF-ACCESS-SIGN: 591a44021fff458a6dfbba517755e1105066864d94c38a0ce84619ae51cf2313' \
--header 'MF-ACCESS-API-KEY: {api key}' \
--header 'MF-ACCESS-TIMESTAMP: 1658737208933' \
--header 'MF-ACCESS-RECV-WINDOW: 5000'
```

```python--pybit

```

> t(:codequote_responseExample)

```javascript
{
    "code": 0,
        "message": "OK",
        "data":  {
        "list": [
            {
                "coin": "USDT",
                "type": "RealisedPNL",
                "amount": "500",
                "walletBalance": "2731.63599033",
                "execTime": "1658215763731"
            }
        ],
            "nextPageCursor": "elZpeUVCSCtFRk5pZjMrMU9reDdMdkpJS2VZdEpqczNHaExPUU5CazA0Yz0="
    },
    "ext_info": {},
    "time": 1658737209400
}
```

t(:wallet_para_walletRecords)


<p class="fake_header">t(:httprequest)</p>
GET
<code><span id=oawfRecordsNew>/private/v1/account/bills</span></code>
<button class="clipboard_button" data-clipboard-action="copy" data-clipboard-target="#oawfRecordsNew"><img src="/images/copy_to_clipboard.png" height=15 width=15></img></button>

<p class="fake_header">t(:requestparameters)</p>
|t(:column_parameter)|t(:column_required)|t(:column_type)|t(:column_comments)|
|:----- |:-------|:-----|----- |
|startTime |false |string |t(:contract_accountStatTime) |
|endTime |false |string |t(:contract_accountEndTime) |
|<a href="#currency-currency-coin">coin</a> |false |string |t(:contract_accountCoin_resp) |
|<a href="#wallet-fund-type-wallet_fund_type-type">walletFundType</a> |false |string |t(:row_comment_walletFundType) |
|limit |false |string |t(:row_comment_limit) |
|cursor |false |string |t(:contract_accountCursor) |


<p class="fake_header">t(:responseparameters)</p>
|t(:column_parameter)|t(:column_type)|t(:column_comments)|
|:----- |:-----|----- |
|list> coin |string |t(:row_comment_coin_type)  |
|list> type |string |t(:row_comment_fund_type)  |
|list> amount |string |t(:row_comment_fund_amount)  |
|list> wallet_balance |string |t(:row_comment_wallet_balance)  |
|list> exec_time |string |t(:row_comment_exec_timestamp)  |
|nextPageCursor |string |t(:contract_accountNextPageCursor)  |

