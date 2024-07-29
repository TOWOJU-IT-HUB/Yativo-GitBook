# Retrieve customer

#### Get Customers Endpoint - Yativo

The <mark style="color:green;">`GET`</mark> `/customer/{{customer_id}}` endpoint allows you to retrieve detailed information about a specific customer using their unique customer ID. This endpoint is useful for accessing and displaying customer data within your application or for performing operations that require customer details.

**Key Features:**

1. **HTTP Method**: `GET`
2. **Endpoint URL**: `/customer/{{customer_id}}`
3. **Authentication**: Requires Bearer token to ensure secure access.

**Response Structure:**

* **Status Code**: `200 OK` on success, with other codes indicating various errors (e.g., `401 Unauthorized`, `404 Not Found`).

**Headers**

<table><thead><tr><th width="413">Name</th><th>Value</th></tr></thead><tbody><tr><td>Content-Type</td><td><code>application/json</code></td></tr><tr><td>Authorization</td><td><code>Bearer &#x3C;token></code></td></tr></tbody></table>

**Request sample and Response**

{% tabs %}
{% tab title="Python" %}
```python
import requests

customer_id = "5ae2f659-45d2-4256-9f82-2811726a5376" //example customer ID
url = f"{{baseUrl}}/customer/{customer_id}"
headers = {
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
}

response = requests.get(url, headers=headers)
print(response.text)

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const customer_id = "5ae2f659-45d2-4256-9f82-2811726a5376"; // example customer ID
const url = `{{baseUrl}}/customer/${customer_id}`;

const options = {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  }
};

fetch(url, options)
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
```php
$customer_id = "5ae2f659-45d2-4256-9f82-2811726a5376"; // example customer ID
$url = "{{baseUrl}}/customer/" . $customer_id;

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

```
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="200" %}
{% code title="success response" lineNumbers="true" %}
```json
{
    "status": "success",
    "status_code": 201,
    "message": "Request successful",
    "data": {
        "customer_id": "5ae2f659-45d2-4256-9f82-2811726a5376",
        "customer_name": "Test Customer",
        "customer_email": "test_customer5@yativo.com",
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
{  "status_code": 400,
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



{% embed url="https://codepen.io/Sotonye-Bob-Manuel/pen/yLdgNmw" %}
