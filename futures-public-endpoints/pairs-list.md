---
description: Get the list of available futures trading pairs on PointPay Exchange.
---

# Pairs List

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/public/trade/pairs`

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/public/trade/pairs" -H "accept: application/json"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name       | Type   | Description  |
| ---------- | ------ | ------------ |
| `asset`    | STRING | Base asset   |
| `quotable` | STRING | Quote asset  |
| `pair`     | STRING | Trading pair |

**Response example:**

```json
{
  "notification": null,
  "warning": null,
  "variables": null,
  "status": "000000",
  "response": [
    {
      "asset": "BTC",
      "quotable": "USDT",
      "pair": "BTCUSDT"
    },
    ...
  ]
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
