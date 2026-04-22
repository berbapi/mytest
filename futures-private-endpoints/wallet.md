---
description: Get the futures wallet balance on PointPay Exchange.
---

# Wallet

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/balance/wallet`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/balance/wallet" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name                         | Type   | Description                                   |
| ---------------------------- | ------ | --------------------------------------------- |
| `totalEquity`                | STRING | Total account equity                          |
| `totalMarginBalance`         | STRING | Total margin balance                          |
| `totalAvailableBalance`      | STRING | Total available balance                       |
| `totalWalletBalance`         | STRING | Total wallet balance                          |
| `totalPerpUPL`               | STRING | Total perpetual unrealized profit and loss    |
| `accountIMRate`              | STRING | Account initial margin rate                   |
| `totalMaintenanceMarginByMp` | STRING | Total maintenance margin by mark price        |
| `totalInitialMargin`         | STRING | Total initial margin                          |
| `accountMMRate`              | STRING | Account maintenance margin rate               |
| `accountMMRateByMp`          | STRING | Account maintenance margin rate by mark price |
| `accountIMRateByMp`          | STRING | Account initial margin rate by mark price     |
| `totalInitialMarginByMp`     | STRING | Total initial margin by mark price            |
| `totalMaintenanceMargin`     | STRING | Total maintenance margin                      |
| `coins`                      | ARRAY  | Wallet balances by coin                       |

Each item in `coins` contains:

| Name               | Type   | Description                         |
| ------------------ | ------ | ----------------------------------- |
| `equity`           | STRING | Coin equity                         |
| `usdValue`         | STRING | Coin value in USD                   |
| `unrealisedPnl`    | STRING | Unrealized profit and loss          |
| `cumRealisedPnl`   | STRING | Cumulative realized profit and loss |
| `walletBalance`    | STRING | Wallet balance                      |
| `availableBalance` | STRING | Available balance                   |
| `totalOrderIM`     | STRING | Total order initial margin          |
| `totalPositionMM`  | STRING | Total position maintenance margin   |
| `totalPositionIM`  | STRING | Total position initial margin       |
| `ticker`           | STRING | Coin ticker                         |
| `name`             | STRING | Coin name                           |
| `image`            | STRING | Coin image URL                      |

**Response example**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "totalEquity": "10.00365",
        "totalMarginBalance": "10.00365",
        "totalAvailableBalance": "10.00365",
        "totalWalletBalance": "10.00365",
        "totalPerpUPL": "0",
        "accountIMRate": "0",
        "totalMaintenanceMarginByMp": "0",
        "totalInitialMargin": "0",
        "accountMMRate": "0",
        "accountMMRateByMp": "0",
        "accountIMRateByMp": "0",
        "totalInitialMarginByMp": "0",
        "totalMaintenanceMargin": "0",
        "coins": [
            {
                "equity": "10.00000",
                "usdValue": "10.00365",
                "unrealisedPnl": "0",
                "cumRealisedPnl": "0",
                "walletBalance": "10.00000",
                "availableBalance": "10.00000",
                "totalOrderIM": "0",
                "totalPositionMM": "0",
                "totalPositionIM": "0",
                "ticker": "USDT",
                "name": "Tether USD",
                "image": "https://pointpay.io/storage/currency/T3wDRn05a7bzOEPJuZYu2l2H7bsOm9V5lbCClEPd.svg"
            },
            {
                "equity": "0",
                "usdValue": "0",
                "unrealisedPnl": "0",
                "cumRealisedPnl": "0",
                "walletBalance": "0",
                "availableBalance": "0",
                "totalOrderIM": "0",
                "totalPositionMM": "0",
                "totalPositionIM": "0",
                "ticker": "USDC",
                "name": "USD Coin",
                "image": "https://pointpay.io/storage/currency/fjN85chuRuhFjoPcfA8v9j7PDU4RSU0elMcmGVKE.svg"
            }
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
