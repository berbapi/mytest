---
description: Get current market data for a futures pair on PointPay Exchange.
---

# Pair Data

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/public/trade/pair-data/{pair}`

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/public/trade/pair-data/BTCUSDT" -H "accept: application/json"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name              | Type   | Description                              |
| ----------------- | ------ | ---------------------------------------- |
| `symbol`          | STRING | Trading pair symbol                      |
| `lastPrice`       | STRING | Last traded price                        |
| `indexPrice`      | STRING | Index price                              |
| `markPrice`       | STRING | Mark price                               |
| `prevPrice24h`    | STRING | Price 24 hours ago                       |
| `price24hPcnt`    | STRING | Price change ratio for the last 24 hours |
| `highPrice24h`    | STRING | Highest price in the last 24 hours       |
| `lowPrice24h`     | STRING | Lowest price in the last 24 hours        |
| `prevPrice1h`     | STRING | Price 1 hour ago                         |
| `turnover24h`     | STRING | Turnover in the last 24 hours            |
| `volume24h`       | STRING | Trading volume in the last 24 hours      |
| `fundingRate`     | STRING | Current funding rate                     |
| `nextFundingTime` | STRING | Next funding time in milliseconds        |

**Response example:**

```json
{
  "notification": null,
  "warning": null,
  "variables": null,
  "status": "000000",
  "response": {
    "symbol": "BTCUSDT",
    "lastPrice": "76799.90",
    "indexPrice": "76833.60",
    "markPrice": "76796.55",
    "prevPrice24h": "74418.90",
    "price24hPcnt": "0.031994",
    "highPrice24h": "76974.00",
    "lowPrice24h": "73235.80",
    "prevPrice1h": "75935.10",
    "turnover24h": "7886904872.8660",
    "volume24h": "105054.2850",
    "fundingRate": "0.00000579",
    "nextFundingTime": "1776441600000"
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
    "path": "/fapi/v1/public/markets-test"
}
```

**This error occurs in the following cases:**

* The requested URL was not found
{% endtab %}
{% endtabs %}
