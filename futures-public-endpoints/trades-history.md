---
description: Get recent public trades for a futures pair on PointPay Exchange.
---

# Trades history

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/public/trade/recent-trade/{pair}`

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/public/trade/recent-trade/BTCUSDT" -H "accept: application/json"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name           | Type    | Description                        |
| -------------- | ------- | ---------------------------------- |
| `execId`       | STRING  | Trade execution ID                 |
| `symbol`       | STRING  | Trading pair symbol                |
| `price`        | STRING  | Trade price                        |
| `size`         | STRING  | Trade size                         |
| `side`         | STRING  | Trade side                         |
| `time`         | STRING  | Trade time in milliseconds         |
| `isBlockTrade` | BOOLEAN | Whether the trade is a block trade |
| `isRPITrade`   | BOOLEAN | Whether the trade is an RPI trade  |
| `seq`          | STRING  | Sequence number                    |

**Response example:**

```json
{
  "notification": null,
  "warning": null,
  "variables": null,
  "status": "000000",
  "response": [
    {
      "execId": "948b8b4b-23b2-5296-97cf-6cbb26f713c9",
      "symbol": "BTCUSDT",
      "price": "73799.60",
      "size": "0.001",
      "side": "Buy",
      "time": "1776640667548",
      "isBlockTrade": false,
      "isRPITrade": false,
      "seq": "563698889054"
    },
    {
      "execId": "011dadb6-ee91-5eda-9cc4-0457ba814d11",
      "symbol": "BTCUSDT",
      "price": "73799.60",
      "size": "0.001",
      "side": "Buy",
      "time": "1776640667548",
      "isBlockTrade": false,
      "isRPITrade": false,
      "seq": "563698889054"
    },
    ...
   ],
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
