# Request Quote

#### Endpoint

`POST {{baseUrl}}/exchange-rate`

#### Description

This endpoint retrieves the exchange rate between two specified currencies. The request must include the source and target currencies, method ID, and method type (either "payin" or "payout"). The request requires bearer token authentication.

#### Request

**Headers**

* **Authorization:** `Bearer YOUR_ACCESS_TOKEN`
* **Content-Type:** `application/json`

**Request Body**

```json
{
    "from_currency" : "USD",
    "to_currency": "GBP",
    "method_id": 331,
    "method_type": "payin"
}

```



{% tabs %}
{% tab title="Python" %}
```python
import requests
import json

url = "{{baseUrl}}/exchange-rate"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json"
}
data = {
    "from_currency": "USD",
    "to_currency": "GBP",
    "method_id": 331,
    "method_type": "payin"
}

response = requests.post(url, headers=headers, data=json.dumps(data))
print(response.json())

```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

$url = "{{baseUrl}}/exchange-rate";
$headers = array(
    "Authorization: Bearer YOUR_ACCESS_TOKEN",
    "Content-Type: application/json"
);
$data = json_encode(array(
    "from_currency" => "USD",
    "to_currency" => "GBP",
    "method_id" => 331,
    "method_type" => "payin"
));

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => $url,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_HTTPHEADER => $headers,
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $data
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

{% tab title="JavaScript" %}
```javascript
const url = "{{baseUrl}}/exchange-rate";

const data = {
  "from_currency": "USD",
  "to_currency": "GBP",
  "method_id": 331,
  "method_type": "payin"
};

const options = {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(data)
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
{% endtabs %}

#### Response

**Example Success Response**

```json
{
  "status": "success",
  "status_code": 200,
  "message": "Exchange rate retrieved successfully",
  "data": {
    "from_currency": "USD",
    "to_currency": "GBP",
    "exchange_rate": 0.75,
    "method_id": 331,
    "method_type": "payin",
    "timestamp": "2024-07-03T12:00:00Z"
  }
}

```
