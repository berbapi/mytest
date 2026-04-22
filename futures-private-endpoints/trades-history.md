---
description: Get futures trade history on PointPay Exchange.
---

# Trades History

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/trade/trades-history`

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
| `execType`    | STRING  | Execution type filter                           | `Trade`           |
| `startTime`   | NUMERIC | Start time in milliseconds                      | `1713542400000`   |
| `endTime`     | NUMERIC | End time in milliseconds                        | `1713628800000`   |

{% hint style="info" %}
`limit` is required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/trade/trades-history?symbol=BTCUSDT&limit=20&startTime=1713542400000&endTime=1713628800000" \
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
| `list`           | ARRAY  | Trade history records |

Each item in `list` contains:

| Name              | Type    | Description                    |
| ----------------- | ------- | ------------------------------ |
| `symbol`          | STRING  | Trading pair                   |
| `orderType`       | STRING  | Order type                     |
| `underlyingPrice` | STRING  | Underlying price               |
| `orderLinkId`     | STRING  | Client order ID                |
| `orderId`         | STRING  | Order ID                       |
| `stopOrderType`   | STRING  | Stop order type                |
| `execTime`        | STRING  | Execution time in milliseconds |
| `feeCurrency`     | STRING  | Fee currency                   |
| `createType`      | STRING  | Order creation source          |
| `execFeeV2`       | STRING  | Execution fee amount           |
| `feeRate`         | STRING  | Fee rate                       |
| `tradeIv`         | STRING  | Trade implied volatility       |
| `blockTradeId`    | STRING  | Block trade ID                 |
| `markPrice`       | STRING  | Mark price                     |
| `execPrice`       | STRING  | Execution price                |
| `markIv`          | STRING  | Mark implied volatility        |
| `orderQty`        | STRING  | Order quantity                 |
| `orderPrice`      | STRING  | Order price                    |
| `execValue`       | STRING  | Execution value                |
| `closedSize`      | STRING  | Closed size                    |
| `execType`        | STRING  | Execution type                 |
| `seq`             | NUMERIC | Trade sequence number          |
| `side`            | STRING  | Order side                     |
| `indexPrice`      | STRING  | Index price                    |
| `leavesQty`       | STRING  | Remaining quantity             |
| `isMaker`         | BOOLEAN | Maker flag                     |
| `execFee`         | STRING  | Execution fee                  |
| `execId`          | STRING  | Execution ID                   |
| `marketUnit`      | STRING  | Market unit                    |
| `execQty`         | STRING  | Executed quantity              |
| `extraFees`       | STRING  | Extra fees                     |
| `execFeeBase`     | STRING  | Execution fee in base terms    |
| `baseCoin`        | STRING  | Base coin                      |
| `quoteCoin`       | STRING  | Quote coin                     |
| `priceScale`      | STRING  | Price precision scale          |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "nextPageCursor": "3658%3A2%2C3068%3A2",
        "category": "linear",
        "list": [
            {
                "symbol": "SNXUSDT",
                "orderType": "Market",
                "underlyingPrice": "",
                "orderLinkId": "fcbe685-e932-48b6-b405-212380245f98",
                "orderId": "f431a04b-c770-4d53-bd32-650a533874f2",
                "stopOrderType": "UNKNOWN",
                "execTime": "1776808216209",
                "feeCurrency": "USDT",
                "createType": "CreateByUser",
                "execFeeV2": "-0.00615188",
                "feeRate": "0.000850000000000000",
                "tradeIv": "",
                "blockTradeId": "",
                "markPrice": "0.2895",
                "execPrice": "0.2895",
                "markIv": "",
                "orderQty": "25",
                "orderPrice": "0.3184",
                "execValue": "7.2375",
                "closedSize": "25",
                "execType": "Trade",
                "seq": 315510924591,
                "side": "Buy",
                "indexPrice": "",
                "leavesQty": "0",
                "isMaker": false,
                "execFee": "0.0061",
                "execId": "d95d0d5a-d3be-5a5f-82d1-a6f10fb8a42f",
                "marketUnit": "",
                "execQty": "25",
                "extraFees": "",
                "execFeeBase": "0.00615188",
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
