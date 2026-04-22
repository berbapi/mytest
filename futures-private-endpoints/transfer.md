---
description: Transfer funds to or from the futures wallet on PointPay Exchange.
---

# Transfer

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/balance/transfer`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name          | Type    | Description                                                        | Example      |
| ------------- | ------- | ------------------------------------------------------------------ | ------------ |
| `ticker`\*    | STRING  | Asset ticker                                                       | `USDT`       |
| `amount`\*    | NUMERIC | Transfer amount                                                    | `100`        |
| `direction`\* | STRING  | Transfer direction. Available values: `TO_FUTURES`, `FROM_FUTURES` | `TO_FUTURES` |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/balance/transfer" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "ticker": "USDT",
    "amount": 100,
    "direction": "TO_FUTURES"
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "message": "futures.balance.success_transfer_request"
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
