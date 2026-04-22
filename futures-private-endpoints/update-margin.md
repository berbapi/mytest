---
description: Manually add or reduce margin for a futures position on PointPay Exchange.
---

# Update Margin

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/update-margin`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name          | Type    | Description                                                                                                                                                                     | Example   |
| ------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| `symbol`\*    | STRING  | Trading pair                                                                                                                                                                    | `BTCUSDT` |
| `margin`\*    | NUMERIC | Add or reduce. To add, then `10`; To reduce, then `-10`. Support up to 4 decimal                                                                                                | `50`      |
| `positionIdx` | INTEGER | <p>Position index. Available values:</p><ul><li><code>0</code>: one-way mode</li><li><code>1</code>: hedge-mode Buy side</li><li><code>2</code>: hedge-mode Sell side</li></ul> | `0`       |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/update-margin" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "BTCUSDT",
    "margin": 50,
    "positionIdx": 0
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name             | Type    | Description                            |
| ---------------- | ------- | -------------------------------------- |
| `category`       | STRING  | Product category                       |
| `positionIdx`    | INTEGER | Position index                         |
| `riskLimitValue` | STRING  | Risk limit value                       |
| `symbol`         | STRING  | Trading pair                           |
| `size`           | STRING  | Position size                          |
| `positionValue`  | STRING  | Position value                         |
| `avgPrice`       | STRING  | Average entry price                    |
| `liqPrice`       | STRING  | Liquidation price                      |
| `bustPrice`      | STRING  | Bankruptcy price                       |
| `markPrice`      | STRING  | Mark price                             |
| `leverage`       | STRING  | Applied leverage                       |
| `autoAddMargin`  | INTEGER | Auto-add-margin flag                   |
| `positionStatus` | STRING  | Position status                        |
| `positionIM`     | STRING  | Initial margin                         |
| `positionMM`     | STRING  | Maintenance margin                     |
| `unrealisedPnl`  | STRING  | Unrealized profit and loss             |
| `cumRealisedPnl` | STRING  | Cumulative realized profit and loss    |
| `takeProfit`     | STRING  | Take-profit price                      |
| `stopLoss`       | STRING  | Stop-loss price                        |
| `trailingStop`   | STRING  | Trailing stop value                    |
| `createdTime`    | STRING  | Position creation time in milliseconds |
| `updatedTime`    | STRING  | Last update time in milliseconds       |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "category": "linear",
        "positionIdx": 0,
        "riskLimitValue": "100000",
        "symbol": "SNXUSDT",
        "size": "25.0",
        "positionValue": "7.24000000",
        "avgPrice": "0.28960000",
        "liqPrice": "0.0795",
        "bustPrice": "0.0779",
        "markPrice": "0.2896",
        "leverage": "25.00",
        "autoAddMargin": 0,
        "positionStatus": "Normal",
        "positionIM": "5.29550784",
        "positionMM": "0.15070784",
        "unrealisedPnl": "0.0",
        "cumRealisedPnl": "-0.10489752",
        "takeProfit": "0.0",
        "stopLoss": "0.0",
        "trailingStop": "0.0",
        "createdTime": "1774506062923",
        "updatedTime": "1779307545414"
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
