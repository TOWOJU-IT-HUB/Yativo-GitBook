# Get Customers

<mark style="color:green;">`GET`</mark> `/customer`

#### Get Customers Endpoint - Yativo

The "Get Customers" endpoint is a crucial part of our API, designed to retrieve detailed information about customers stored in the system. This endpoint provides an efficient way for applications to access customer data for various purposes, including displaying customer profiles, analyzing customer demographics, or integrating with other systems.

**Key Features:**

1. **HTTP Method**: `GET`
2. **Endpoint URL**: `{{baseUrl}}/customer`
3. **Authentication**: Requires API key or OAuth token to ensure secure access.
4. **Query Parameters**:
   * `per_page` (optional): The page number for paginated results.

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

{% tab title="JavaScript" %}
```javascript
const url = '{{baseUrl}}/customer';
const options = {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  }
};

fetch(url, options)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => '{{baseUrl}}/customer',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_HTTPHEADER => array(
    'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  ),
));

$response = curl_exec($curl);
curl_close($curl);

echo $response;
?>

```
{% endtab %}
{% endtabs %}



{% tabs %}
{% tab title="200" %}
<pre class="language-json" data-title="Success response" data-line-numbers><code class="lang-json"><strong>{
</strong>    "status": "success",
    "status_code": 200,
    "message": "Records retrieved successfully",
    "data": [
        {
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
        },
        {
            "customer_id": "3f103e55-1dc5-40bd-a78c-a4574f4a50e0"
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
    ],
    "pagination": {
        "total": 2,
        "per_page": 20,
        "current_page": 1,
        "last_page": 1,
        "next_page_url": null,
        "prev_page_url": null
    }
}
</code></pre>
{% endtab %}

{% tab title="400" %}
```json
{   "status_code": 400,
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



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/customer" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% openapi src="broken-reference" path="/customer" method="get" %}
[Broken link](broken-reference)
{% endopenapi %}
