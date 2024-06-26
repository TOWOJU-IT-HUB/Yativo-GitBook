---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Virtual Accounts



## Create virtual account

<mark style="color:green;">`POST`</mark> `/users`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name   | Type   | Description      |
| ------ | ------ | ---------------- |
| `name` | string | Name of the user |
| `age`  | number | Age of the user  |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "status": "success",
    "status_code": 201,
    "message": "Virtual account creation in progress",
    "data": {
        "account_id": "va_67890",
        "account_number": "9876543210",
        "account_type": "savings",
        "currency": "USD",
        "created_at": "2023-05-27T14:45:00Z"
    }
}

```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}
