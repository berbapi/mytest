---
description: Get futures positions on PointPay Exchange.
---

# Positions

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/trade/positions`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Query Parameters**

| Name          | Type    | Description                                          | Example          |
| ------------- | ------- | ---------------------------------------------------- | ---------------- |
| `symbol`      | STRING  | Trading pair                                         | `BTCUSDT`        |
| `orderId`     | STRING  | Order ID                                             | `1736254849204`  |
| `orderLinkId` | STRING  | Client order ID                                      | `client-order-1` |
| `openOnly`    | NUMERIC | Open positions filter                                | `1`              |
| `orderFilter` | STRING  | Filter value. Available values: `Order`, `StopOrder` | `Order`          |

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/trade/positions?symbol=BTCUSDT&openOnly=1&orderFilter=Order" \
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

| Name                     | Type    | Description                            |
| ------------------------ | ------- | -------------------------------------- |
| `symbol`                 | STRING  | Trading pair                           |
| `leverage`               | STRING  | Applied leverage                       |
| `breakEvenPrice`         | STRING  | Break-even price                       |
| `autoAddMargin`          | INTEGER | Auto-add-margin flag                   |
| `avgPrice`               | STRING  | Average entry price                    |
| `liqPrice`               | STRING  | Liquidation price                      |
| `riskLimitValue`         | STRING  | Risk limit value                       |
| `takeProfit`             | STRING  | Take-profit price                      |
| `positionValue`          | STRING  | Position value                         |
| `isReduceOnly`           | BOOLEAN | Reduce-only flag                       |
| `positionIMByMp`         | STRING  | Initial margin by mark price           |
| `tpslMode`               | STRING  | TP/SL mode                             |
| `riskId`                 | INTEGER | Risk tier ID                           |
| `trailingStop`           | STRING  | Trailing stop value                    |
| `unrealisedPnl`          | STRING  | Unrealized profit and loss             |
| `markPrice`              | STRING  | Mark price                             |
| `adlRankIndicator`       | INTEGER | ADL rank indicator                     |
| `cumRealisedPnl`         | STRING  | Cumulative realized profit and loss    |
| `positionMM`             | STRING  | Maintenance margin                     |
| `createdTime`            | STRING  | Position creation time in milliseconds |
| `positionIdx`            | INTEGER | Position index                         |
| `openTime`               | NUMERIC | Position open time in milliseconds     |
| `positionIM`             | STRING  | Initial margin                         |
| `positionMMByMp`         | STRING  | Maintenance margin by mark price       |
| `seq`                    | NUMERIC | Position sequence number               |
| `updatedTime`            | STRING  | Last update time in milliseconds       |
| `side`                   | STRING  | Position side                          |
| `bustPrice`              | STRING  | Bankruptcy price                       |
| `positionBalance`        | STRING  | Position balance                       |
| `leverageSysUpdatedTime` | STRING  | Leverage system update time            |
| `curRealisedPnl`         | STRING  | Current realized profit and loss       |
| `size`                   | STRING  | Position size                          |
| `positionStatus`         | STRING  | Position status                        |
| `mmrSysUpdatedTime`      | STRING  | Margin rate system update time         |
| `stopLoss`               | STRING  | Stop-loss price                        |
| `tradeMode`              | INTEGER | Trade mode                             |
| `sessionAvgPrice`        | STRING  | Session average price                  |
| `baseCoin`               | STRING  | Base coin                              |
| `quoteCoin`              | STRING  | Quote coin                             |
| `priceScale`             | STRING  | Price precision scale                  |
| `feeOpenCurrency`        | STRING  | Fee currency for opening               |
| `openFee`                | STRING  | Opening fee                            |

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
            "leverage": "25",
            "breakEvenPrice": "0.29039324",
            "autoAddMargin": 0,
            "avgPrice": "0.2899",
            "liqPrice": "0.0000",
            "riskLimitValue": "100000",
            "takeProfit": "",
            "positionValue": "7.2475",
            "isReduceOnly": false,
            "positionIMByMp": "0.29581396",
            "tpslMode": "Full",
            "riskId": 1091,
            "trailingStop": "0",
            "unrealisedPnl": "0",
            "markPrice": "0.2899",
            "adlRankIndicator": 2,
            "cumRealisedPnl": "-0.08508952",
            "positionMM": "0.15086396",
            "createdTime": "1776806062923",
            "positionIdx": 0,
            "openTime": 1746806610164,
            "positionIM": "0.29581396",
            "positionMMByMp": "0.15086396",
            "seq": 314509385153,
            "updatedTime": "1766806610164",
            "side": "Buy",
            "bustPrice": "",
            "positionBalance": "0",
            "leverageSysUpdatedTime": "",
            "curRealisedPnl": "-0.0122",
            "size": "25",
            "positionStatus": "Normal",
            "mmrSysUpdatedTime": "",
            "stopLoss": "",
            "tradeMode": 0,
            "sessionAvgPrice": "",
            "baseCoin": "SNX",
            "quoteCoin": "USDT",
            "priceScale": "4",
            "feeOpenCurrency": "USDT",
            "openFee": "0.0061"
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
