---
hidden: true
---

# Create Multiple Virtual Accounts

## Create virtual account

<mark style="color:green;">`POST`</mark> `{{baseUrl}}/business/virtual-account/bulk-account-creation`This endpoint allows you to create a virtual account that can be used to receive funds.

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

**Request Example**



{% tabs %}
{% tab title="PHP" %}
```php
<?php
$baseUrl = 'https://sandbox.yativo.com'; // Replace with the actual base URL
$accessToken = 'YOUR_ACCESS_TOKEN';
$customerId = 'YOUR_CUSTOMER_ID';

$url = $baseUrl . '/business/virtual-account/bulk-account-creation';

$data = [
    'customer_id' => $customerId,
    'beneficiary' => [
        'document' => [
            'id' => 'A10909999',
            'type' => 'PASSPORT'
        ],
        'name' => 'xoxo',
        'lastname' => 'xoxo',
        'type' => 'xoxo'
    ],
    'address' => [
        'city' => 'xoxo',
        'state' => 'xoxo',
        'zipcode' => 'xoxo',
        'street' => 'xoxo',
        'number' => 'xoxo',
        'country' => 'xoxo'
    ],
    'currency' => 'MXN',
    'country' => 'MEX'
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
{% endtabs %}

{% swagger src="broken-reference" path="/business/virtual-account/bulk-account-creation" method="post" %}
[Broken link](broken-reference)
{% endswagger %}
