---
description: Get active futures orders on PointPay Exchange.
---

# Active Orders

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/trade/orders`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Query Parameters**

| Name          | Type    | Description                                          | Example          |
| ------------- | ------- | ---------------------------------------------------- | ---------------- |
| `symbol`      | STRING  | Trading pair                                         | `BTCUSDT`        |
| `orderId`     | STRING  | Order ID                                             | `1736254849204`  |
| `orderLinkId` | STRING  | Client order ID                                      | `client-order-1` |
| `openOnly`    | NUMERIC | Open orders filter                                   | `1`              |
| `orderFilter` | STRING  | Order filter. Available values: `Order`, `StopOrder` | `Order`          |

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/trade/orders?symbol=BTCUSDT&openOnly=1&orderFilter=Order" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

Each item in `response` contains:

| Name                 | Type    | Description                         |
| -------------------- | ------- | ----------------------------------- |
| `symbol`             | STRING  | Trading pair                        |
| `orderType`          | STRING  | Order type                          |
| `orderLinkId`        | STRING  | Client order ID                     |
| `slLimitPrice`       | STRING  | Stop-loss limit price               |
| `orderId`            | STRING  | Order ID                            |
| `cancelType`         | STRING  | Cancel type                         |
| `avgPrice`           | STRING  | Average executed price              |
| `stopOrderType`      | STRING  | Stop order type                     |
| `lastPriceOnCreated` | STRING  | Last price at creation time         |
| `orderStatus`        | STRING  | Order status                        |
| `createType`         | STRING  | Order creation source               |
| `takeProfit`         | STRING  | Take-profit price                   |
| `cumExecValue`       | STRING  | Cumulative executed value           |
| `tpslMode`           | STRING  | TP/SL mode                          |
| `smpType`            | STRING  | Self-match prevention type          |
| `triggerDirection`   | INTEGER | Trigger direction                   |
| `blockTradeId`       | STRING  | Block trade ID                      |
| `cumFeeDetail`       | ARRAY   | Cumulative fee details              |
| `isLeverage`         | STRING  | Leverage mode flag                  |
| `rejectReason`       | STRING  | Reject reason                       |
| `price`              | STRING  | Order price                         |
| `orderIv`            | STRING  | Implied volatility                  |
| `createdTime`        | STRING  | Order creation time in milliseconds |
| `tpTriggerBy`        | STRING  | Take-profit trigger source          |
| `positionIdx`        | INTEGER | Position index                      |
| `timeInForce`        | STRING  | Time in force                       |
| `leavesValue`        | STRING  | Remaining order value               |
| `updatedTime`        | STRING  | Last update time in milliseconds    |
| `side`               | STRING  | Order side                          |
| `smpGroup`           | INTEGER | Self-match prevention group         |
| `triggerPrice`       | STRING  | Trigger price                       |
| `tpLimitPrice`       | STRING  | Take-profit limit price             |
| `cumExecFee`         | STRING  | Cumulative executed fee             |
| `leavesQty`          | STRING  | Remaining quantity                  |
| `slTriggerBy`        | STRING  | Stop-loss trigger source            |
| `closeOnTrigger`     | BOOLEAN | Close-on-trigger flag               |
| `placeType`          | STRING  | Placement type                      |
| `cumExecQty`         | STRING  | Cumulative executed quantity        |
| `reduceOnly`         | BOOLEAN | Reduce-only flag                    |
| `qty`                | STRING  | Order quantity                      |
| `stopLoss`           | STRING  | Stop-loss price                     |
| `marketUnit`         | STRING  | Market unit                         |
| `smpOrderId`         | STRING  | Self-match prevention order ID      |
| `parentOrderLinkId`  | STRING  | Parent client order ID              |
| `triggerBy`          | STRING  | Trigger price source                |
| `pair`               | OBJECT  | Pair metadata                       |

`pair` contains:

| Name            | Type   | Description             |
| --------------- | ------ | ----------------------- |
| `id`            | STRING | Pair ID                 |
| `name`          | STRING | Pair name               |
| `leftCurrency`  | OBJECT | Base currency metadata  |
| `rightCurrency` | OBJECT | Quote currency metadata |

`leftCurrency` and `rightCurrency` contain:

| Name     | Type   | Description        |
| -------- | ------ | ------------------ |
| `ticker` | STRING | Currency ticker    |
| `img`    | STRING | Currency image URL |
| `label`  | STRING | Currency name      |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": [
        {
            "symbol": "SNXUSDT",
            "orderType": "Limit",
            "orderLinkId": "6a57c401-e731-4a14-8dd1-ebae9ee14c72",
            "slLimitPrice": "0",
            "orderId": "f24f61ac-52a6-4785-9e46-410cd10deaab",
            "cancelType": "UNKNOWN",
            "avgPrice": "",
            "stopOrderType": "",
            "lastPriceOnCreated": "0.2895",
            "orderStatus": "New",
            "createType": "CreateByUser",
            "takeProfit": "",
            "cumExecValue": "0",
            "tpslMode": "",
            "smpType": "None",
            "triggerDirection": 0,
            "blockTradeId": "",
            "cumFeeDetail": [],
            "isLeverage": "",
            "rejectReason": "EC_NoError",
            "price": "0.2897",
            "orderIv": "",
            "createdTime": "1674808224264",
            "tpTriggerBy": "",
            "positionIdx": 0,
            "timeInForce": "GTC",
            "leavesValue": "7.2425",
            "updatedTime": "1676868224267",
            "side": "Sell",
            "smpGroup": 0,
            "triggerPrice": "",
            "tpLimitPrice": "0",
            "cumExecFee": "0",
            "leavesQty": "25",
            "slTriggerBy": "",
            "closeOnTrigger": false,
            "placeType": "",
            "cumExecQty": "0",
            "reduceOnly": false,
            "qty": "25",
            "stopLoss": "",
            "marketUnit": "",
            "smpOrderId": "",
            "parentOrderLinkId": "",
            "triggerBy": "",
            "pair": {
                "id": "SNXUSDT",
                "name": "SNXUSDT",
                "leftCurrency": {
                    "ticker": "SNX",
                    "img": "https://pointpay.io/storage/currency/hDYLbvcp63Rt6NXo0IcksNYoWJ7ZqxX4zgAxkviA.svg",
                    "label": "Synthetix Network Token"
                },
                "rightCurrency": {
                    "ticker": "USDT",
                    "img": "https://pointpay.io/storage/currency/T3wDRn05a7bzOEPJuZYu2l2H7bsOm9V5lbCClEPd.svg",
                    "label": "Tether USD"
                }
            }
        }
    ],
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
