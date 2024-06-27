# Update customer data



<mark style="color:green;">`PUT`</mark> `/customer/{{customer_id}}`

#### Get Customers Endpoint - Yativo

The "Get Customers" endpoint is a crucial part of our API, designed to retrieve detailed information about customers stored in the system. This endpoint provides an efficient way for applications to access customer data for various purposes, including displaying customer profiles, analyzing customer demographics, or integrating with other systems.

**Key Features:**

1. **HTTP Method**: PU`T`
2. **Endpoint URL**: `/customer/{{customer_id}}`
3. **Authentication**: Requires Bearer token to ensure secure access.

**Response Structure:**

* **Status Code**: `200 OK` on success, with other codes indicating various errors (e.g., `401 Unauthorized`, `404 Not Found`).

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Request sample and Response**

{% tabs %}
{% tab title="Request" %}
```python
import requests

url = "{{baseUrl}}/customer"

payload = {}
headers = {
  'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```
{% endtab %}

{% tab title="200" %}
{% code title="success response" lineNumbers="true" fullWidth="true" %}
```json
{
    "status": "success",
    "status_code": 200,
    "message": "Records retrieved successfully",
    "data": {
        "customer_id": "2f103e55-1dc5-40bd-a78c-a4574f7a50e6",
        "customer_name": "Test Customer",
        "customer_email": "test_customer@yativo.com",
        "customer_phone": "+19203751411",
        "customer_country": "USA",
        "customer_address": {
            "city": "Anytown",
            "state": "Anystate",
            "zipcode": "12345",
            "street": "1234 Elm Street",
            "number": "5678",
            "country": "USA"
        }
    }
}
```
{% endcode %}
{% endtab %}

{% tab title="400" %}
```json
    "status_code": 400,
    "message": "Request failed",
    "data": {
        "error": "Oops. Error message"
    }
}
```
{% endtab %}

{% tab title="401" %}
```json
{
    "message": "Unauthenticated."
}
```
{% endtab %}
{% endtabs %}
