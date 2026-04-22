---
description: Set the futures margin mode on PointPay Exchange.
---

# Set Margin Mode

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/margin-mode`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name     | Type   | Description                                                        | Example           |
| -------- | ------ | ------------------------------------------------------------------ | ----------------- |
| `mode`\* | STRING | Margin mode. Available values: `ISOLATED_MARGIN`, `REGULAR_MARGIN` | `ISOLATED_MARGIN` |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/margin-mode" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "mode": "ISOLATED_MARGIN"
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name       | Type  | Description                                    |
| ---------- | ----- | ---------------------------------------------- |
| `response` | ARRAY | Empty array returned when the request succeeds |

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
