---
description: Set leverage for a futures pair on PointPay Exchange.
---

# Set Leverage

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/leverage`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name         | Type    | Description    | Example   |
| ------------ | ------- | -------------- | --------- |
| `symbol`\*   | STRING  | Trading pair   | `BTCUSDT` |
| `leverage`\* | NUMERIC | Leverage value | `10`      |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/leverage" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "BTCUSDT",
    "leverage": 10
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name       | Type   | Description      |
| ---------- | ------ | ---------------- |
| `leverage` | STRING | Applied leverage |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "leverage": "25"
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
