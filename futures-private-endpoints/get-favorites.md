---
description: Get the list of favorite futures pairs on PointPay Exchange.
---

# Get Favorites

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/favorites`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/favorites" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

Each item in `response` contains:

| Name | Type   | Description   |
| ---- | ------ | ------------- |
| item | STRING | Favorite pair |

**Response example:**

```json
{
    "response": [
        "BTCUSDT"
    ],
    "status": 201,
    "errors": null,
    "notification": null,
    "warning": null,
    "variables": null
}
```
{% endtab %}
{% endtabs %}
