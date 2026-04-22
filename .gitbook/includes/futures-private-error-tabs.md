---
title: Futures private error tabs
---

**Response example**

```json
{
    "code": 400,
    "success": false,
    "message": "invalid input",
    "result": []
}
```

Returned when the request is invalid.

Common reasons:

* Invalid request format
* Invalid headers

**Response example**

```json
{"code":400,"success":false,"message":"authentication failure","result":[]}
```

Returned when authentication headers are missing / invalid or API Keys are not enabled.
