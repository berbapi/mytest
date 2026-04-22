---
description: Update a chase order on PointPay Exchange.
---

# Chase Order

#### Details <a href="#details" id="details"></a>

`POST` `https://api.pointpay.io/fapi/v1/private/trade/chase-order`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Request Body**

| Name        | Type    | Description         | Example         |
| ----------- | ------- | ------------------- | --------------- |
| `orderId`\* | STRING  | Order ID            | `1736254849204` |
| `price`     | NUMERIC | Updated chase price | `65000`         |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X POST "https://api.pointpay.io/fapi/v1/private/trade/chase-order" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>" \
  -H "Content-Type: application/json" \
  -d '{
    "orderId": "1736254849204",
    "price": 65000
  }'
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name          | Type   | Description      |
| ------------- | ------ | ---------------- |
| `orderId`     | STRING | Updated order ID |
| `orderLinkId` | STRING | System order ID  |

**Response example:**

```json
{
    "notification": null,
    "warning": null,
    "variables": null,
    "status": "000000",
    "response": {
        "orderId": "6ac24069-2bd7-4ed4-8b4e-8d62fa564b3c",
        "orderLinkId": "4e15dca7-9d58-486b-8eae-13ceeaf849ad"
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
