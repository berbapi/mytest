---
description: Create a futures order on PointPay Exchange.
---

# Create Order

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/create-order`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name               | Type    | Description                                                                          | Example     |
| ------------------ | ------- | ------------------------------------------------------------------------------------ | ----------- |
| `symbol`\*         | STRING  | Trading pair                                                                         | `BTCUSDT`   |
| `side`\*           | STRING  | Order side. Available values: `Buy`, `Sell`                                          | `Buy`       |
| `orderType`\*      | STRING  | Order type. Available values: `Market`, `Limit`                                      | `Limit`     |
| `qty`\*            | NUMERIC | Order quantity                                                                       | `0.01`      |
| `price`            | NUMERIC | Order price                                                                          | `65000`     |
| `triggerDirection` | INTEGER | Trigger direction. Available values: `1`, `2`                                        | `1`         |
| `triggerPrice`     | NUMERIC | Trigger price                                                                        | `64000`     |
| `triggerBy`        | STRING  | Trigger price source. Available values: `LastPrice`, `IndexPrice`, `MarkPrice`       | `MarkPrice` |
| `positionIdx`      | INTEGER | Position index. Available values: `0`, `1`, `2`                                      | `0`         |
| `takeProfit`       | NUMERIC | Take-profit price                                                                    | `68000`     |
| `stopLoss`         | NUMERIC | Stop-loss price                                                                      | `62000`     |
| `tpTriggerBy`      | STRING  | Take-profit trigger source. Available values: `LastPrice`, `IndexPrice`, `MarkPrice` | `MarkPrice` |
| `slTriggerBy`      | STRING  | Stop-loss trigger source. Available values: `LastPrice`, `IndexPrice`, `MarkPrice`   | `MarkPrice` |
| `reduceOnly`       | BOOLEAN | Reduce-only flag                                                                     | `false`     |
| `tpslMode`         | STRING  | TP/SL mode. Available values: `Full`, `Partial`                                      | `Full`      |
| `tpLimitPrice`     | NUMERIC | Take-profit limit price                                                              | `67950`     |
| `slLimitPrice`     | NUMERIC | Stop-loss limit price                                                                | `62050`     |
| `tpOrderType`      | STRING  | Take-profit order type. Available values: `Limit`, `Market`                          | `Limit`     |
| `slOrderType`      | STRING  | Stop-loss order type. Available values: `Limit`, `Market`                            | `Market`    |
| `timeInForce`      | STRING  | Time in force. Available values: `GTC`, `IOC`, `FOK`, `PostOnly`, `RPI`              | `GTC`       |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/create-order" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "BTCUSDT",
    "side": "Buy",
    "orderType": "Limit",
    "qty": 0.01,
    "price": 65000,
    "timeInForce": "GTC"
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name          | Type   | Description      |
| ------------- | ------ | ---------------- |
| `orderId`     | STRING | Created order ID |
| `orderLinkId` | STRING | System order ID  |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "orderId": "6ac24069-2bd7-4ed4-8b4e-8d62fa564b3c",
        "orderLinkId": "4e15dca7-9d58-486b-8eae-13ceeaf849ad"
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
