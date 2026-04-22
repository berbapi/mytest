---
title: Futures private authentication headers
---

**Headers**

| Name                | Type   | Description                              |
| ------------------- | ------ | ---------------------------------------- |
| `X-TXC-APIKEY`\*    | STRING | Public API key                           |
| `X-TXC-PAYLOAD`\*   | STRING | Base64-encoded request body              |
| `X-TXC-SIGNATURE`\* | STRING | HmacSHA512 signature of the request body |
