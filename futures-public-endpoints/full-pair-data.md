---
description: Get full market and instrument data for a futures pair on PointPay Exchange.
---

# Full Pair Data

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/public/trade/full-pair-data/{pair}`

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/public/trade/full-pair-data/BTCUSDT" -H "accept: application/json"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name                                          | Type    | Description                               |
| --------------------------------------------- | ------- | ----------------------------------------- |
| `trade_data.symbol`                           | STRING  | Trading pair symbol                       |
| `trade_data.lastPrice`                        | STRING  | Last traded price                         |
| `trade_data.indexPrice`                       | STRING  | Index price                               |
| `trade_data.markPrice`                        | STRING  | Mark price                                |
| `trade_data.prevPrice24h`                     | STRING  | Price 24 hours ago                        |
| `trade_data.price24hPcnt`                     | STRING  | Price change ratio for the last 24 hours  |
| `trade_data.highPrice24h`                     | STRING  | Highest price in the last 24 hours        |
| `trade_data.lowPrice24h`                      | STRING  | Lowest price in the last 24 hours         |
| `trade_data.prevPrice1h`                      | STRING  | Price 1 hour ago                          |
| `trade_data.openInterest`                     | STRING  | Open interest                             |
| `trade_data.openInterestValue`                | STRING  | Open interest value                       |
| `trade_data.turnover24h`                      | STRING  | Turnover in the last 24 hours             |
| `trade_data.volume24h`                        | STRING  | Trading volume in the last 24 hours       |
| `trade_data.fundingRate`                      | STRING  | Current funding rate                      |
| `trade_data.nextFundingTime`                  | STRING  | Next funding time in milliseconds         |
| `trade_data.ask1Size`                         | STRING  | Best ask size                             |
| `trade_data.bid1Price`                        | STRING  | Best bid price                            |
| `trade_data.ask1Price`                        | STRING  | Best ask price                            |
| `trade_data.bid1Size`                         | STRING  | Best bid size                             |
| `trade_data.fundingIntervalHour`              | STRING  | Funding interval in hours                 |
| `trade_data.fundingCap`                       | STRING  | Funding rate cap                          |
| `pair_data.symbol`                            | STRING  | Trading pair symbol                       |
| `pair_data.contractType`                      | STRING  | Contract type                             |
| `pair_data.status`                            | STRING  | Pair status                               |
| `pair_data.baseCoin`                          | STRING  | Base asset code                           |
| `pair_data.quoteCoin`                         | STRING  | Quote asset code                          |
| `pair_data.launchTime`                        | STRING  | Launch time in milliseconds               |
| `pair_data.deliveryFeeRate`                   | STRING  | Delivery fee rate                         |
| `pair_data.priceScale`                        | STRING  | Price precision                           |
| `pair_data.leverageFilter.minLeverage`        | STRING  | Minimum leverage                          |
| `pair_data.leverageFilter.maxLeverage`        | STRING  | Maximum leverage                          |
| `pair_data.leverageFilter.leverageStep`       | STRING  | Leverage step                             |
| `pair_data.priceFilter.minPrice`              | STRING  | Minimum order price                       |
| `pair_data.priceFilter.maxPrice`              | STRING  | Maximum order price                       |
| `pair_data.priceFilter.tickSize`              | STRING  | Price tick size                           |
| `pair_data.lotSizeFilter.maxOrderQty`         | STRING  | Maximum order quantity                    |
| `pair_data.lotSizeFilter.minOrderQty`         | STRING  | Minimum order quantity                    |
| `pair_data.lotSizeFilter.qtyStep`             | STRING  | Quantity step                             |
| `pair_data.lotSizeFilter.postOnlyMaxOrderQty` | STRING  | Maximum post-only order quantity          |
| `pair_data.lotSizeFilter.maxMktOrderQty`      | STRING  | Maximum market order quantity             |
| `pair_data.lotSizeFilter.minNotionalValue`    | STRING  | Minimum notional order value              |
| `pair_data.fundingInterval`                   | NUMERIC | Funding interval in minutes               |
| `pair_data.settleCoin`                        | STRING  | Settlement coin                           |
| `pair_data.upperFundingRate`                  | STRING  | Upper funding rate limit                  |
| `pair_data.lowerFundingRate`                  | STRING  | Lower funding rate limit                  |
| `pair_data.isPreListing`                      | BOOLEAN | Whether the pair is in pre-listing status |
| `pair_data.riskParameters.priceLimitRatioX`   | STRING  | Price limit ratio X                       |
| `pair_data.riskParameters.priceLimitRatioY`   | STRING  | Price limit ratio Y                       |
| `pair_data.displayName`                       | STRING  | Pair display name                         |
| `pair_data.symbolType`                        | STRING  | Symbol type                               |

**Response example:**

```json
{
  "notification": null,
  "warning": null,
  "variables": null,
  "status": "000000",
  "response": {
    "trade_data": {
      "symbol": "BTCUSDT",
      "lastPrice": "73877.10",
      "indexPrice": "73917.13",
      "markPrice": "73880.70",
      "prevPrice24h": "75800.70",
      "price24hPcnt": "-0.025377",
      "highPrice24h": "76211.80",
      "lowPrice24h": "73700.10",
      "prevPrice1h": "73839.00",
      "openInterest": "48937.122",
      "openInterestValue": "3615508829.35",
      "turnover24h": "4229196028.5439",
      "volume24h": "56310.6590",
      "fundingRate": "-0.00003008",
      "nextFundingTime": "1776643200000",
      "ask1Size": "2.949",
      "bid1Price": "73877.00",
      "ask1Price": "73877.10",
      "bid1Size": "1.728",
      "fundingIntervalHour": "8",
      "fundingCap": "0.005"
    },
    "pair_data": {
      "symbol": "BTCUSDT",
      "contractType": "LinearPerpetual",
      "status": "Trading",
      "baseCoin": "BTC",
      "quoteCoin": "USDT",
      "launchTime": "1584230400000",
      "deliveryFeeRate": "",
      "priceScale": "2",
      "leverageFilter": {
        "minLeverage": "1",
        "maxLeverage": "100.00",
        "leverageStep": "0.01"
      },
      "priceFilter": {
        "minPrice": "0.10",
        "maxPrice": "1999999.80",
        "tickSize": "0.10"
      },
      "lotSizeFilter": {
        "maxOrderQty": "1500.000",
        "minOrderQty": "0.001",
        "qtyStep": "0.001",
        "postOnlyMaxOrderQty": "1500.000",
        "maxMktOrderQty": "150.000",
        "minNotionalValue": "5"
      },
      "fundingInterval": 480,
      "settleCoin": "USDT",
      "upperFundingRate": "0.005",
      "lowerFundingRate": "-0.005",
      "riskParameters": {
        "priceLimitRatioX": "0.01",
        "priceLimitRatioY": "0.02"
      },
      "displayName": "",
      "symbolType": ""
    }
  },
  "errors": null
}
```
{% endtab %}

{% tab title="400: Bad Request" %}
**Response example:**

```html
<html>

<head>
	<title>400 Bad Request</title>
</head>

<body>
	<center>
		<h1>400 Bad Request</h1>
	</center>
	<hr>
	<center>nginx</center>
</body>

</html>
```

**This error occurs in the following cases:**

* Invalid URL
* Request contains invalid headers
{% endtab %}

{% tab title="404: Not Found" %}
**Response example:**

```javascript
{
    "timestamp": 1660766043722,
    "status": 404,
    "error": "Not Found",
    "message": "",
    "path": "/fapi/v1/public/trade/markets-test"
}
```

**This error occurs in the following cases:**

* The requested URL was not found
{% endtab %}
{% endtabs %}
