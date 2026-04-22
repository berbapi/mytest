---
description: Update TP, SL, and related position settings on PointPay Exchange.
---

# Update Position

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/update-position`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name            | Type    | Description                                                                                                                                                                     | Example     |
| --------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| `symbol`\*      | STRING  | Trading pair                                                                                                                                                                    | `BTCUSDT`   |
| `tpslMode`\*    | STRING  | TP/SL mode. Available values: `Full`, `Partial`                                                                                                                                 | `Full`      |
| `positionIdx`\* | INTEGER | <p>Position index. Available values:</p><ul><li><code>0</code>: one-way mode</li><li><code>1</code>: hedge-mode Buy side</li><li><code>2</code>: hedge-mode Sell side</li></ul> | `0`         |
| `takeProfit`    | NUMERIC | Take-profit price                                                                                                                                                               | `68000`     |
| `stopLoss`      | NUMERIC | Stop-loss price                                                                                                                                                                 | `62000`     |
| `trailingStop`  | NUMERIC | Trailing stop value                                                                                                                                                             | `150`       |
| `tpTriggerBy`   | STRING  | Take-profit trigger source. Available values: `LastPrice`, `IndexPrice`, `MarkPrice`                                                                                            | `MarkPrice` |
| `slTriggerBy`   | STRING  | Stop-loss trigger source. Available values: `LastPrice`, `IndexPrice`, `MarkPrice`                                                                                              | `MarkPrice` |
| `activePrice`   | NUMERIC | Active price for trailing stop                                                                                                                                                  | `64500`     |
| `tpSize`        | NUMERIC | Take-profit size                                                                                                                                                                | `0.01`      |
| `slSize`        | NUMERIC | Stop-loss size                                                                                                                                                                  | `0.01`      |
| `tpLimitPrice`  | NUMERIC | Take-profit limit price                                                                                                                                                         | `67950`     |
| `slLimitPrice`  | NUMERIC | Stop-loss limit price                                                                                                                                                           | `62050`     |
| `tpOrderType`   | STRING  | Take-profit order type. Available values: `Market`, `Limit`                                                                                                                     | `Limit`     |
| `slOrderType`   | STRING  | Stop-loss order type. Available values: `Market`, `Limit`                                                                                                                       | `Market`    |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/update-position" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "BTCUSDT",
    "tpslMode": "Full",
    "positionIdx": 0,
    "takeProfit": 68000,
    "stopLoss": 62000
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
Empty array returned when the request succeeds

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": [],
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
