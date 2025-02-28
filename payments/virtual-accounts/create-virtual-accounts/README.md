# Create VIrtual Accounts

## Create virtual account

<mark style="color:green;">`POST`</mark> `{{baseUrl}}`/business/virtual-account/create

This endpoint allows you to create a virtual account that can be used to receive funds.

KYC must have been completed by the customer before this can be enabled.

Each customer can have only 1 Virtual account per currency

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |



{% openapi src="../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/business/virtual-account/create" method="post" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

**Body**

| Name          | Type   | Description   |
| ------------- | ------ | ------------- |
| `customer_id` | number | Customer ID   |
| `currency`    | string | USD, MXN, BRL |

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

**Request Example**



{% tabs %}
{% tab title="PHP" %}
```php
<?php
$baseUrl = 'https://sandbox.yativo.com'; // Replace with the actual base URL
$accessToken = 'YOUR_ACCESS_TOKEN';
$customerId = 'YOUR_CUSTOMER_ID';

$url = $baseUrl . '/example-endpoint';

$data = [
    "currency": "USD", // supported are BRL, MXN,
    "customer_id": "ae68f0ef-0e59-4a23-b8da-9e07bf2af361"
    ];

$options = [
    'http' => [
        'header'  => "Authorization: Bearer $accessToken\r\n" .
                     "Content-Type: application/json\r\n",
        'method'  => 'POST',
        'content' => json_encode($data)
    ]
];

$context  = stream_context_create($options);
$response = file_get_contents($url, false, $context);

if ($response === FALSE) {
    die('Error occurred');
}

$responseData = json_decode($response, true);
print_r($responseData);
?>

```
{% endtab %}

{% tab title="Python" %}
```python
import requests

baseUrl = 'https://sandbox.yativo.com'  # Replace with the actual base URL
accessToken = 'YOUR_ACCESS_TOKEN'
customerId = 'YOUR_CUSTOMER_ID'
url = f'{baseUrl}/example-endpoint'

data = {
    "currency": "USD", // supported are BRL, MXN,
    "customer_id": "ae68f0ef-0e59-4a23-b8da-9e07bf2af361"
}

headers = {
    'Authorization': f'Bearer {accessToken}',
    'Content-Type': 'application/json'
}

response = requests.post(url, json=data, headers=headers)

if response.status_code != 200:
    print(f'Error: {response.status_code} - {response.text}')
else:
    responseData = response.json()
    print('Response:', responseData)

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const baseUrl = 'https://sandbox.yativo.com'; // Replace with the actual base URL
const accessToken = 'YOUR_ACCESS_TOKEN';
const customerId = 'YOUR_CUSTOMER_ID';
const url = `${baseUrl}/example-endpoint`;

const data = {
    "currency": "USD", // supported are BRL, MXN,
    "customer_id": "ae68f0ef-0e59-4a23-b8da-9e07bf2af361"
};

const options = {
  method: 'POST',
  headers: {
    'Authorization': `Bearer ${accessToken}`,
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(data)
};

fetch(url, options)
  .then(response => {
    if (!response.ok) {
      throw new Error(`Network response was not ok ${response.statusText}`);
    }
    return response.json();
  })
  .then(data => console.log('Response:', data))
  .catch(error => console.error('Error:', error));
```
{% endtab %}
{% endtabs %}

{% openapi src="broken-reference" path="/business/virtual-account/create" method="post" %}
[Broken link](broken-reference)
{% endopenapi %}
