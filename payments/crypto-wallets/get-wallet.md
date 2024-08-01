# Get Wallet

#### API Documentation

**Endpoint**: `POST {{baseUrl}}/crypto`

**Authorization**: Bearer Token

**Request Body**:

```json
{
    "currency": "USDT.TRC20"
}
```

Example Request&#x20;

{% tabs %}
{% tab title="PHP" %}
```php
<?php
$baseUrl = 'https://api.yativo.com';
$accessToken = 'YOUR_ACCESS_TOKEN';

$url = $baseUrl . '/crypto';

$data = [
    'currency' => 'USDT.TRC20'
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
import json

baseUrl = 'https://api.yativo.com'
accessToken = 'YOUR_ACCESS_TOKEN'
url = f'{baseUrl}/crypto'

data = {
    'currency': 'USDT.TRC20'
}

headers = {
    'Authorization': f'Bearer {accessToken}',
    'Content-Type': 'application/json'
}

response = requests.post(url, headers=headers, data=json.dumps(data))

if response.status_code != 200:
    print(f'Error: {response.status_code} - {response.text}')
else:
    responseData = response.json()
    print('Wallet address generated:', responseData)
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const baseUrl = 'https://api.yativo.com';
const accessToken = 'YOUR_ACCESS_TOKEN';
const url = `${baseUrl}/crypto`;

const data = {
  currency: 'USDT.TRC20'
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
  .then(data => console.log('Wallet address generated:', data))
  .catch(error => console.error('Error:', error));

```
{% endtab %}
{% endtabs %}

{% embed url="https://codepen.io/Sotonye-Bob-Manuel/pen/ExBWxNa" %}
