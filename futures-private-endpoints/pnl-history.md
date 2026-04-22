---
description: Get futures PnL history on PointPay Exchange.
---

# PnL History

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/trade/pnl-history`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Query Parameters**

| Name        | Type    | Description                                     | Example           |
| ----------- | ------- | ----------------------------------------------- | ----------------- |
| `symbol`    | STRING  | Trading pair                                    | `BTCUSDT`         |
| `startTime` | NUMERIC | Start time in milliseconds                      | `1713542400000`   |
| `endTime`   | NUMERIC | End time in milliseconds                        | `1713628800000`   |
| `limit`\*   | NUMERIC | Number of records to return. Range: `1` to `50` | `20`              |
| `cursor`    | STRING  | Cursor for paginated results                    | `next-page-token` |

{% hint style="info" %}
`limit` is required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/trade/pnl-history?symbol=BTCUSDT&limit=20&startTime=1713542400000&endTime=1713628800000" \
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

| Name             | Type   | Description          |
| ---------------- | ------ | -------------------- |
| `nextPageCursor` | STRING | Cursor for next page |
| `category`       | STRING | Product category     |
| `list`           | ARRAY  | PnL history records  |

Each item in `list` contains:

| Name               | Type    | Description                      |
| ------------------ | ------- | -------------------------------- |
| `symbol`           | STRING  | Trading pair                     |
| `orderType`        | STRING  | Order type                       |
| `leverage`         | STRING  | Applied leverage                 |
| `updatedTime`      | STRING  | Last update time in milliseconds |
| `side`             | STRING  | Order side                       |
| `orderId`          | STRING  | Order ID                         |
| `closedPnl`        | NUMERIC | Closed profit and loss           |
| `openFee`          | STRING  | Opening fee                      |
| `closeFee`         | STRING  | Closing fee                      |
| `avgEntryPrice`    | STRING  | Average entry price              |
| `qty`              | STRING  | Order quantity                   |
| `cumEntryValue`    | STRING  | Cumulative entry value           |
| `createdTime`      | STRING  | Creation time in milliseconds    |
| `orderPrice`       | STRING  | Order price                      |
| `closedSize`       | STRING  | Closed size                      |
| `avgExitPrice`     | STRING  | Average exit price               |
| `execType`         | STRING  | Execution type                   |
| `fillCount`        | STRING  | Number of fills                  |
| `cumExitValue`     | STRING  | Cumulative exit value            |
| `feeOpenCurrency`  | STRING  | Opening fee currency             |
| `feeCloseCurrency` | STRING  | Closing fee currency             |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "nextPageCursor": "f881a08b-c770-4d53-bd21-640a533874f2%3A1776808216212%2Ce15798fe-a255-4efe-9d45-f2d6e15c1c33%3A1776806100794",
        "category": "linear",
        "list": [
            {
                "symbol": "SNXUSDT",
                "orderType": "Market",
                "leverage": "25",
                "updatedTime": "1776808216212",
                "side": "Buy",
                "orderId": "f881a08b-c770-4d53-bd21-640a533874f2",
                "closedPnl": -0.01469999999999945,
                "openFee": "0.0036",
                "closeFee": "0.0061",
                "avgEntryPrice": "0.2893",
                "qty": "25",
                "cumEntryValue": "7.2325",
                "createdTime": "1776808216208",
                "orderPrice": "0.3184",
                "closedSize": "25",
                "avgExitPrice": "0.2895",
                "execType": "Trade",
                "fillCount": "1",
                "cumExitValue": "7.2375",
                "feeOpenCurrency": "USDT",
                "feeCloseCurrency": "USDT"
            },
            ...
         ]
    },
    "errors": null
}
```
{% endtab %}
{% endtabs %}
