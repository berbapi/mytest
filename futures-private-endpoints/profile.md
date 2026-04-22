---
description: Get the futures profile on PointPay Exchange.
---

# Profile

#### Details <a href="#details" id="details"></a>

`GET` `https://api.pointpay.io/fapi/v1/private/profile`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X GET "https://api.pointpay.io/fapi/v1/private/profile" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name              | Type  | Description                          |
| ----------------- | ----- | ------------------------------------ |
| `allowedCurrency` | ARRAY | List of supported futures currencies |

Each item in `allowedCurrency` contains:

| Name     | Type   | Description        |
| -------- | ------ | ------------------ |
| `name`   | STRING | Currency name      |
| `ticker` | STRING | Currency ticker    |
| `image`  | STRING | Currency image URL |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "allowedCurrency": [
            {
                "name": "Tether USD",
                "ticker": "USDT",
                "image": "https://pointpay.io/storage/currency/T3wDRn05a7bzOEPJuZYu2l2H7bsOm9V5lbCClEPd.svg"
            },
            {
                "name": "USD Coin",
                "ticker": "USDC",
                "image": "https://pointpay.io/storage/currency/fjN85chuRuhFjoPcfA8v9j7PDU4RSU0elMcmGVKE.svg"
            }
        ]
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
