---
description: Set the futures position mode on PointPay Exchange.
---

# Change Position Mode

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/position-mode`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name         | Type   | Description                                                  | Example      |
| ------------ | ------ | ------------------------------------------------------------ | ------------ |
| `mode`\*     | STRING | Position mode. Available values: `SINGLEMODE`, `HEDGEMODE`   | `SINGLEMODE` |
| `pairMode`\* | STRING | Scope of the mode change. Available values: `ALL`, `CURRENT` | `CURRENT`    |
| `symbol`\*   | STRING | Trading pair                                                 | `BTCUSDT`    |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/position-mode" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "mode": "SINGLEMODE",
    "pairMode": "CURRENT",
    "symbol": "BTCUSDT"
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
Empty array returned when the request succeeds

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": [],
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
