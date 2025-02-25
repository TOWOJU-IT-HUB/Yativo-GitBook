---
hidden: true
---

# Update customer data

#### Update Customer Endpoint - Yativo

The <mark style="color:green;">`PUT`</mark> `/customer/{{customer_id}}` endpoint provides an efficient way for applications to update the details of an existing customer in the Yativo system. This endpoint is used when you need to modify specific information associated with a customer.

**Key Features:**

1. **HTTP Method**: `PUT`
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
{% tab title="Python" %}
```
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

{% tab title="JavaScript" %}
```
const url = '{{baseUrl}}/customer';
const headers = {
  'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
};

fetch(url, {
  method: 'GET',
  headers: headers
})
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok ' + response.statusText);
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

```
{% endtab %}

{% tab title="PHP" %}
```
<?php
$url = '{{baseUrl}}/customer';
$headers = array(
    'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
);

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => $url,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_HTTPHEADER => $headers
));

$response = curl_exec($curl);

if (curl_errno($curl)) {
    echo 'Error:' . curl_error($curl);
} else {
    echo $response;
}

curl_close($curl);
?>

```
{% endtab %}
{% endtabs %}

{% tabs %}
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

