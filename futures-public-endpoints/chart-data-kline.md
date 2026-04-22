---
description: Get candlestick chart data for a futures pair on PointPay Exchange.
---

# Chart Data Kline

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/public/trade/kline`

**Query Parameters**

<table><thead><tr><th width="174.05078125">Name</th><th>Type</th><th>Description</th><th>Example</th></tr></thead><tbody><tr><td>symbol<mark style="color:red;">*</mark></td><td>STRING</td><td>Symbol name, uppercase only</td><td>BTCUSDT</td></tr><tr><td>interval<mark style="color:red;">*</mark></td><td>STRING</td><td>Time interval (1,3,5,15,30,60,120,240,360,720,D,W,M)</td><td>1</td></tr><tr><td>start</td><td>NUMERIC</td><td>Start time (unixtime, ms)</td><td>1660638764</td></tr><tr><td>end</td><td>NUMERIC</td><td>End time (unixtime, ms)</td><td>1660818764</td></tr><tr><td>limit</td><td>NUMERIC</td><td>Limit for data size per page. [1, 1000]. Default: 200</td><td>200</td></tr></tbody></table>

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/public/trade/kline?symbol=BTCUSDT&interval=1" -H "accept: application/json"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

Each item in `response` contains:

| Name  | Type   | Description                      |
| ----- | ------ | -------------------------------- |
| `[0]` | STRING | Candle open time in milliseconds |
| `[1]` | STRING | Open price                       |
| `[2]` | STRING | High price                       |
| `[3]` | STRING | Low price                        |
| `[4]` | STRING | Close price                      |
| `[5]` | STRING | Trading volume                   |
| `[6]` | STRING | Turnover                         |

**Response example:**

```json
{
  "notification": null,
  "warning": null,
  "variables": null,
  "status": "000000",
  "response": [
    [
      "1776641280000",
      "73880.4",
      "73890.5",
      "73853",
      "73870.5",
      "8.74",
      "645664.9228"
    ],
    [
      "1776641220000",
      "73876.4",
      "73887.5",
      "73856.8",
      "73880.4",
      "10.057",
      "742947.8511"
    ],
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
