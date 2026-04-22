---
description: Get futures pair parameters and user settings on PointPay Exchange.
---

# Pair Params

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/trade/pair-params/{pair}`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Path Parameters**

| Name     | Type   | Description  | Example   |
| -------- | ------ | ------------ | --------- |
| `pair`\* | STRING | Trading pair | `BTCUSDT` |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/trade/pair-params/BTCUSDT" \
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

| Name               | Type    | Description                        |
| ------------------ | ------- | ---------------------------------- |
| `symbol`           | STRING  | Trading pair                       |
| `displayName`      | STRING  | Pair display name                  |
| `baseCoin`         | STRING  | Base coin                          |
| `quoteCoin`        | STRING  | Quote coin                         |
| `launchTime`       | STRING  | Pair launch time in milliseconds   |
| `fundingInterval`  | INTEGER | Funding interval in minutes        |
| `leverage`         | OBJECT  | Allowed leverage range             |
| `price`            | OBJECT  | Allowed price range                |
| `priceScale`       | STRING  | Price precision scale              |
| `orderSize`        | OBJECT  | Order size limits                  |
| `settleCoin`       | STRING  | Settlement coin                    |
| `upperFundingRate` | STRING  | Upper funding rate limit           |
| `lowerFundingRate` | STRING  | Lower funding rate limit           |
| `riskParameters`   | OBJECT  | Risk parameter ratios              |
| `takerFeeRate`     | STRING  | Taker fee rate                     |
| `makerFeeRate`     | STRING  | Maker fee rate                     |
| `user`             | OBJECT  | Current user settings for the pair |

`leverage` contains:

| Name           | Type   | Description      |
| -------------- | ------ | ---------------- |
| `minLeverage`  | STRING | Minimum leverage |
| `maxLeverage`  | STRING | Maximum leverage |
| `leverageStep` | STRING | Leverage step    |

`price` contains:

| Name       | Type   | Description     |
| ---------- | ------ | --------------- |
| `minPrice` | STRING | Minimum price   |
| `maxPrice` | STRING | Maximum price   |
| `tickSize` | STRING | Price tick size |

`orderSize` contains:

| Name                | Type   | Description               |
| ------------------- | ------ | ------------------------- |
| `maxOrderQty`       | STRING | Maximum limit order size  |
| `minOrderQty`       | STRING | Minimum order size        |
| `maxMarketOrderQty` | STRING | Maximum market order size |
| `step`              | STRING | Order size step           |
| `minOrderAmount`    | STRING | Minimum order amount      |

`riskParameters` contains:

| Name               | Type   | Description         |
| ------------------ | ------ | ------------------- |
| `priceLimitRatioX` | STRING | Price limit ratio X |
| `priceLimitRatioY` | STRING | Price limit ratio Y |

`user` contains:

| Name           | Type   | Description        |
| -------------- | ------ | ------------------ |
| `marginMode`   | STRING | User margin mode   |
| `leverage`     | STRING | User leverage      |
| `positionMode` | STRING | User position mode |

**Response example:**

```json
{
   "notification": null,
   "warning": null,
   "variables": null,
   "status": "000000",
   "response": {
       "symbol": "SNXUSDT",
       "displayName": "",
       "baseCoin": "SNX",
       "quoteCoin": "USDT",
       "launchTime": "1639357278000",
       "fundingInterval": 480,
       "leverage": {
           "minLeverage": "1",
           "maxLeverage": "25.00",
           "leverageStep": "0.01"
       },
       "price": {
           "minPrice": "0.0001",
           "maxPrice": "1999.9998",
           "tickSize": "0.0001"
       },
       "priceScale": "4",
       "orderSize": {
           "maxOrderQty": "175120.0",
           "minOrderQty": "0.1",
           "maxMarketOrderQty": "35660.0",
           "step": "0.1",
           "minOrderAmount": "5"
       },
       "settleCoin": "USDT",
       "upperFundingRate": "0.02",
       "lowerFundingRate": "-0.02",
       "riskParameters": {
           "priceLimitRatioX": "0.1",
           "priceLimitRatioY": "0.2"
       },
       "takerFeeRate": "0.00076500",
       "makerFeeRate": "0.00045000",
       "user": {
           "marginMode": "REGULAR_MARGIN",
           "leverage": "25.00",
           "positionMode": "SINGLEMODE"
       }
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
