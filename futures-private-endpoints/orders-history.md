---
description: Get futures order history on PointPay Exchange.
---

# Orders History

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/trade/orders-history`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Query Parameters**

| Name          | Type    | Description                                     | Example           |
| ------------- | ------- | ----------------------------------------------- | ----------------- |
| `symbol`      | STRING  | Trading pair                                    | `BTCUSDT`         |
| `settleCoin`  | STRING  | Settlement coin                                 | `USDT`            |
| `orderId`     | STRING  | Order ID                                        | `1736254849204`   |
| `orderLinkId` | STRING  | Client order ID                                 | `client-order-1`  |
| `limit`\*     | NUMERIC | Number of records to return. Range: `1` to `50` | `20`              |
| `cursor`      | STRING  | Cursor for paginated results                    | `next-page-token` |
| `orderStatus` | STRING  | Order status filter                             | `Filled`          |
| `startTime`   | NUMERIC | Start time in milliseconds                      | `1713542400000`   |
| `endTime`     | NUMERIC | End time in milliseconds                        | `1713628800000`   |

{% hint style="info" %}
`limit` is required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/trade/orders-history?symbol=BTCUSDT&limit=20&startTime=1713542400000&endTime=1713628800000" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

`response` contains:

| Name             | Type   | Description           |
| ---------------- | ------ | --------------------- |
| `nextPageCursor` | STRING | Cursor for next page  |
| `category`       | STRING | Product category      |
| `list`           | ARRAY  | Order history records |

Each item in `list` contains:

| Name                    | Type    | Description                         |
| ----------------------- | ------- | ----------------------------------- |
| `symbol`                | STRING  | Trading pair                        |
| `orderType`             | STRING  | Order type                          |
| `orderLinkId`           | STRING  | Client order ID                     |
| `slLimitPrice`          | STRING  | Stop-loss limit price               |
| `orderId`               | STRING  | Order ID                            |
| `cancelType`            | STRING  | Cancel type                         |
| `avgPrice`              | STRING  | Average executed price              |
| `stopOrderType`         | STRING  | Stop order type                     |
| `lastPriceOnCreated`    | STRING  | Last price at creation time         |
| `orderStatus`           | STRING  | Order status                        |
| `createType`            | STRING  | Order creation source               |
| `takeProfit`            | STRING  | Take-profit price                   |
| `cumExecValue`          | STRING  | Cumulative executed value           |
| `tpslMode`              | STRING  | TP/SL mode                          |
| `smpType`               | STRING  | Self-match prevention type          |
| `triggerDirection`      | INTEGER | Trigger direction                   |
| `blockTradeId`          | STRING  | Block trade ID                      |
| `cumFeeDetail`          | OBJECT  | Cumulative fee details by currency  |
| `rejectReason`          | STRING  | Reject reason                       |
| `isLeverage`            | STRING  | Leverage mode flag                  |
| `price`                 | STRING  | Order price                         |
| `orderIv`               | STRING  | Implied volatility                  |
| `createdTime`           | STRING  | Order creation time in milliseconds |
| `tpTriggerBy`           | STRING  | Take-profit trigger source          |
| `positionIdx`           | INTEGER | Position index                      |
| `timeInForce`           | STRING  | Time in force                       |
| `leavesValue`           | STRING  | Remaining order value               |
| `updatedTime`           | STRING  | Last update time in milliseconds    |
| `side`                  | STRING  | Order side                          |
| `smpGroup`              | INTEGER | Self-match prevention group         |
| `triggerPrice`          | STRING  | Trigger price                       |
| `tpLimitPrice`          | STRING  | Take-profit limit price             |
| `cumExecFee`            | STRING  | Cumulative executed fee             |
| `slTriggerBy`           | STRING  | Stop-loss trigger source            |
| `leavesQty`             | STRING  | Remaining quantity                  |
| `closeOnTrigger`        | BOOLEAN | Close-on-trigger flag               |
| `slippageToleranceType` | STRING  | Slippage tolerance type             |
| `placeType`             | STRING  | Placement type                      |
| `cumExecQty`            | STRING  | Cumulative executed quantity        |
| `reduceOnly`            | BOOLEAN | Reduce-only flag                    |
| `qty`                   | STRING  | Order quantity                      |
| `stopLoss`              | STRING  | Stop-loss price                     |
| `smpOrderId`            | STRING  | Self-match prevention order ID      |
| `parentOrderLinkId`     | STRING  | Parent client order ID              |
| `slippageTolerance`     | STRING  | Slippage tolerance value            |
| `triggerBy`             | STRING  | Trigger price source                |
| `extraFees`             | STRING  | Extra fees                          |
| `feeCurrency`           | STRING  | Fee currency                        |
| `cumExecFeeBase`        | STRING  | Executed fee in base terms          |
| `cumExecFeeSystem`      | STRING  | System fee amount                   |
| `baseCoin`              | STRING  | Base coin                           |
| `quoteCoin`             | STRING  | Quote coin                          |
| `priceScale`            | STRING  | Price precision scale               |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "nextPageCursor": "f881a08b-c770-4d53-bd21-640a533874f2%3A1776808216208%2Cc5e4452d-6fa6-4453-bc9f-d6bcc795b90f%3A1776807519069",
        "category": "linear",
        "list": [
            {
                "symbol": "SNXUSDT",
                "orderType": "Market",
                "orderLinkId": "fcbe6955-e472-48b6-b405-212380245f98",
                "slLimitPrice": "0",
                "orderId": "f881a08b-c770-4d53-bd21-640a533874f2",
                "cancelType": "UNKNOWN",
                "avgPrice": "0.2895",
                "stopOrderType": "",
                "lastPriceOnCreated": "0.2895",
                "orderStatus": "Filled",
                "createType": "CreateByUser",
                "takeProfit": "",
                "cumExecValue": "7.2375",
                "tpslMode": "",
                "smpType": "None",
                "triggerDirection": 0,
                "blockTradeId": "",
                "cumFeeDetail": {
                    "USDT": "0.00615188"
                },
                "rejectReason": "EC_NoError",
                "isLeverage": "",
                "price": "0.3184",
                "orderIv": "",
                "createdTime": "1776808216208",
                "tpTriggerBy": "",
                "positionIdx": 0,
                "timeInForce": "IOC",
                "leavesValue": "0",
                "updatedTime": "1776808216212",
                "side": "Buy",
                "smpGroup": 0,
                "triggerPrice": "",
                "tpLimitPrice": "0",
                "cumExecFee": "0.0061",
                "slTriggerBy": "",
                "leavesQty": "0",
                "closeOnTrigger": false,
                "slippageToleranceType": "UNKNOWN",
                "placeType": "",
                "cumExecQty": "25",
                "reduceOnly": true,
                "qty": "25",
                "stopLoss": "",
                "smpOrderId": "",
                "parentOrderLinkId": "",
                "slippageTolerance": "0",
                "triggerBy": "",
                "extraFees": "",
                "feeCurrency": "USDT",
                "cumExecFeeBase": "0.00615188",
                "cumExecFeeSystem": "0.000000000000000000",
                "baseCoin": "SNX",
                "quoteCoin": "USDT",
                "priceScale": "4"
            },
            ...
          ]
    },
    "errors": null
}     
```
{% endtab %}

{% tab title="400: Bad Request" %}
{% include "../.gitbook/includes/futures-private-400-response.md" %}
{% endtab %}

{% tab title="401: Unauthorized" %}
{% include "../.gitbook/includes/futures-private-401-response.md" %}
{% endtab %}
{% endtabs %}
