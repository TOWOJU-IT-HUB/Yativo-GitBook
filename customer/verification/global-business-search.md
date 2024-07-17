# Global Business Search

**What is Global Business Search?**

The Global Business Search endpoint allows you to search for business entities across the globe. This can be useful for verifying the existence, registration status, and details of companies in various countries. This endpoint helps businesses ensure compliance and verify the legitimacy of other business entities.

* **Endpoint:** `POST {{baseUrl}}/verification/business-search`
* **Description:** Perform a search for global business entities.
* **Headers:**
  * `Authorization: Bearer YOUR_API_KEY`
  * `Content-Type: application/json`

**Request Parameters:**

| Parameter             | Type   | Required | Description                                |
| --------------------- | ------ | -------- | ------------------------------------------ |
| `business_name`       | string | Yes      | The name of the business to search for.    |
| `country`             | string | Yes      | The country where the business is located. |
| `registration_number` | string | No       | The registration number of the business.   |
| `address`             | string | No       | The address of the business.               |
| `phone`               | string | No       | The phone number of the business.          |
| `email`               | string | No       | The email address of the business.         |

```json
{
    "business_name": "Yativo Inc.",
    "country": "US",
    "registration_number": "123456789",
    "address": "123 Business St, Business City, State, 12345",
    "phone": "+1234567890",
    "email": "contact@yativo.com"
}
```

#### Error Codes

The API uses standard HTTP status codes to indicate the success or failure of an API request. The following table provides details of common error codes:

| Status Code | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| 200         | Request was successful.                                     |
| 400         | Bad request. The request parameters are invalid or missing. |
| 401         | Unauthorized. The API key is missing or invalid.            |
| 403         | Forbidden. You do not have access to this resource.         |
| 404         | Not found. The requested resource could not be found.       |
| 500         | Internal server error. An error occurred on the server.     |



{% tabs %}
{% tab title="Python" %}
```python
import requests

url = "{{baseUrl}}/verification/business-search"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}
data = {
    "business_name": "Yativo Inc.",
    "country": "US",
    "registration_number": "123456789",
    "address": "123 Business St, Business City, State, 12345",
    "phone": "+1234567890",
    "email": "contact@yativo.com"
}

response = requests.post(url, json=data, headers=headers)
print(response.json())
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

$url = "{{baseUrl}}/verification/business-search";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];
$data = [
    "business_name" => "Yativo Inc.",
    "country" => "US",
    "registration_number" => "123456789",
    "address" => "123 Business St, Business City, State, 12345",
    "phone" => "+1234567890",
    "email" => "contact@yativo.com"
];

$options = [
    "http" => [
        "header" => implode("\r\n", $headers),
        "method" => "POST",
        "content" => json_encode($data),
    ]
];

$context = stream_context_create($options);
$response = file_get_contents($url, false, $context);
if ($response === FALSE) {
    die('Error');
}

echo $response;
?>
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = '{{baseUrl}}/verification/business-search';
const headers = {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
};
const data = {
    business_name: 'Yativo Inc.',
    country: 'US',
    registration_number: '123456789',
    address: '123 Business St, Business City, State, 12345',
    phone: '+1234567890',
    email: 'contact@yativo.com'
};

fetch(url, {
    method: 'POST',
    headers: headers,
    body: JSON.stringify(data)
})
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));
```
{% endtab %}
{% endtabs %}
