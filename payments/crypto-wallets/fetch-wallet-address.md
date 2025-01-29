# Fetch Wallet Address

This endpoint helps fetch all crypto wallet addresses in the system tied to your account

**Endpoint**: `GET {{baseUrl}}/crypto/get-wallets`

**Authorization**: Bearer Token

**Response Example**:

```json
[
    {
        "currency": "USDT.TRC20",
        "address": "TXYZ1234ABC5678EFG9012HIJKL3456MNO789PQR",
        "balance": 100.0
    },
    {
        "currency": "BTC",
        "address": "1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa",
        "balance": 0.5
    }
]
```

```json
{
    "error": "Invalid authorization token"
}
```



**Request Example**

{% tabs %}
{% tab title="PHP" %}
```php
<?php
$baseUrl = 'https://api.yativo.com';
$accessToken = 'YOUR_ACCESS_TOKEN';

$url = $baseUrl . '/crypto/get-wallets';

$options = [
    'http' => [
        'header'  => "Authorization: Bearer $accessToken\r\n",
        'method'  => 'GET'
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
// Some code
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

baseUrl = 'https://api.yativo.com'
accessToken = 'YOUR_ACCESS_TOKEN'
url = f'{baseUrl}/crypto/get-wallets'

headers = {
    'Authorization': f'Bearer {accessToken}'
}

response = requests.get(url, headers=headers)

if response.status_code != 200:
    print(f'Error: {response.status_code} - {response.text}')
else:
    responseData = response.json()
    print('Crypto wallets:', responseData)

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const baseUrl = 'https://api.yativo.com';
const accessToken = 'YOUR_ACCESS_TOKEN';
const url = `${baseUrl}/crypto/get-wallets`;

const options = {
  method: 'GET',
  headers: {
    'Authorization': `Bearer ${accessToken}`
  }
};

fetch(url, options)
  .then(response => {
    if (!response.ok) {
      throw new Error(`Network response was not ok ${response.statusText}`);
    }
    return response.json();
  })
  .then(data => console.log('Crypto wallets:', data))
  .catch(error => console.error('Error:', error));

```
{% endtab %}
{% endtabs %}



{% swagger src="broken-reference" path="/crypto/get-wallets" method="get" %}
[Broken link](broken-reference)
{% endswagger %}
