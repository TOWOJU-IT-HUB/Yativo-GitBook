# Create Multiple VIrtual Accounts

## Create virtual account

<mark style="color:green;">`POST`</mark> `{{baseUrl}}/customer/virtual-accounts/create`

This endpoint allows you to create a virtual account that can be used to receive funds.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name            | Type   | Description        |
| --------------- | ------ | ------------------ |
| `customer_id`   | number | Customer ID        |
| `document_id`   | string | Document Id number |
| `document_type` | string | The Document type  |
| `currency`      | string | USD, ARS, MXN, BRL |

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
