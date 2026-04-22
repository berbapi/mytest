---
description: Add a futures pair to favorites on PointPay Exchange.
---

# Add Favorite

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/favorites`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name     | Type   | Description                      | Example   |
| -------- | ------ | -------------------------------- | --------- |
| `pair`\* | STRING | Trading pair to add to favorites | `BTCUSDT` |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/favorites" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "pair": "BTCUSDT"
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name      | Type   | Description               |
| --------- | ------ | ------------------------- |
| `message` | STRING | Result message identifier |

**Response example:**

```json
{
    "response": {
        "message": "futures.favoritePair.delete.success"
    },
    "status": 201,
    "errors": null,
    "notification": null,
    "warning": null,
    "variables": null
}
```
{% endtab %}
{% endtabs %}
