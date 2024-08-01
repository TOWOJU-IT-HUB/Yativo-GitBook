# Delete Customer

#### DELETE Customer Endpoint - Yativo

The <mark style="color:green;">`DELETE`</mark> `/customer/{{customer_id}}` endpoint allows you to delete a specific customer profile using their unique customer ID. This endpoint is useful for closing a customer account within your application or for performing operations that require customer details.

**Key Features:**

1. **HTTP Method**: `DELETE`
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
```python
import requests

customer_id = "5ae2f659-45d2-4256-9f82-2811726a5376" //example customer ID
url = f"{{baseUrl}}/customer/{customer_id}"
headers = {
    "Authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
}

response = requests.delete(url, headers=headers)
print(response.text)

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const customer_id = "5ae2f659-45d2-4256-9f82-2811726a5376"; // example customer ID
const url = `{{baseUrl}}/customer/${customer_id}`;

const options = {
  method: 'DELETE',
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
  CURLOPT_CUSTOMREQUEST => "DELETE",
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
  "message": "Customer successfully deleted"
}
```
{% endcode %}
{% endtab %}

{% tab title="404" %}
```
{
  "error": "Customer not found"
}

```
{% endtab %}

{% tab title="401" %}
```
{
  "error": "Unauthorized access"
}
```
{% endtab %}
{% endtabs %}



{% embed url="https://codepen.io/Sotonye-Bob-Manuel/pen/yLdgYre" %}
