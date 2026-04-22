---
description: Remove a futures pair from favorites on PointPay Exchange.
---

# Delete Favorite

#### Details <a href="#details" id="details"></a>

`DELETE` `https://api.pointpay.io/fapi/v1/private/favorites/{id}`

{% include "../.gitbook/includes/futures-private-authentication-headers.md" %}

**Path Parameters**

| Name     | Type   | Description | Example |
| -------- | ------ | ----------- | ------- |
| `pair`\* | STRING | Pair        | BTCUSDT |

{% hint style="info" %}
Fields marked with `*` are required.
{% endhint %}

<details>

<summary>CURL Example</summary>

```hurl
curl -X DELETE "https://api.pointpay.io/fapi/v1/private/favorites/1" \
  -H "accept: application/json" \
  -H "X-TXC-APIKEY: <api-key>" \
  -H "X-TXC-PAYLOAD: <base64-payload>" \
  -H "X-TXC-SIGNATURE: <signature>"
```

</details>

{% tabs %}
{% tab title="200: OK Successful" %}
**Response parameters:**

| Name          | Type   | Description        |
| ------------- | ------ | ------------------ |
| `orderId`     | STRING | Response ID        |
| `orderLinkId` | STRING | Client response ID |

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
{% endtabs %}
