---
description: Get current order book data for a futures pair on PointPay Exchange.
---

# Order Book Data

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/public/trade/order-book/{pair}`

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/public/trade/order-book/BTCUSDT" -H "accept: application/json"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name  | Type    | Description                               |
| ----- | ------- | ----------------------------------------- |
| `s`   | STRING  | Trading pair symbol                       |
| `b`   | ARRAY   | Bid levels as `[price, size]` pairs       |
| `a`   | ARRAY   | Ask levels as `[price, size]` pairs       |
| `ts`  | NUMERIC | Response timestamp in milliseconds        |
| `u`   | NUMERIC | Update ID                                 |
| `seq` | NUMERIC | Sequence number                           |
| `cts` | NUMERIC | Matching engine timestamp in milliseconds |

**Response example:**

```json
{
  "notification": null,
  "warning": null,
  "variables": null,
  "status": "000000",
  "response": {
    "s": "BTCUSDT",
    "b": [
      [
        "73988.5",
        "3.608"
      ],
      [
        "73988.4",
        "0.001"
      ],
      [
        "73987.2",
        "0.003"
      ],
    ...
    ],
    "a": [
      [
        "73988.6",
        "3.464"
      ],
      [
        "73988.7",
        "0.001"
      ],
      ...
    ],
    "ts": 1776640498623,
    "u": 17587500,
    "seq": 563697531117,
    "cts": 1776640498616
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
