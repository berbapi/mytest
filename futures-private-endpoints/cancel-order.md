---
description: Cancel a futures order on PointPay Exchange.
---

# Cancel Order

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/cancel-order`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name          | Type   | Description                                       | Example                              |
| ------------- | ------ | ------------------------------------------------- | ------------------------------------ |
| `symbol`\*    | STRING | Trading pair                                      | `BTCUSDT`                            |
| `orderId`     | STRING | Order ID. Required if `orderLinkId` is not set.   | 6ac24069-2bd7-4ed4-8b4e-8d62fa564b3c |
| `orderLinkId` | STRING | System order ID. Required if `orderId` is not set | 6ac24069-2bd7-4ed4-8b4e-8d62fa564b3c |

{% hint style="info" %}
`symbol` is required. Send either `orderId` or `orderLinkId`.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/cancel-order" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "symbol": "BTCUSDT",
    "orderId": "1736254849204"
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
