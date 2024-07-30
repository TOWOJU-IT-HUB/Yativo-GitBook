---
description: List of Currencies supported by the system
---

# Currencies

`GET {{baseUrl}}/currencies/all`

#### Description

This endpoint retrieves a list of all currencies supported on the system for Payout, Payin, Wallet, Sub Wallet, Currency Swap and Virtual Accounts.

#### Request

**Headers**

* **Authorization:** `Bearer YOUR_ACCESS_TOKEN`

**Request Body**

No request body is required for this endpoint.



{% tabs %}
{% tab title="Python" %}
```python
import requests

url = "{{baseUrl}}/currencies/all"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN"
}

response = requests.get(url, headers=headers)
print(response.json())

```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

$url = "{{baseUrl}}/currencies/all";
$headers = array(
    "Authorization: Bearer YOUR_ACCESS_TOKEN"
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

{% tab title="JavaScript" %}
```javascript
const url = "{{baseUrl}}/currencies/all";

const options = {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
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

{% tab title="cURL" %}
```xml
curl -X GET "{{baseUrl}}/currencies/all" \
     -H "Authorization: Bearer YOUR_ACCESS_TOKEN"

```
{% endtab %}
{% endtabs %}

**Success response**

```json
{
  "status": "success",
  "status_code": 200,
  "message": "Request successful",
  "data": [
    {
      "id": 1,
      "wallet": "USD",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "$",
      "currency_name": "United State Dollars",
      "balance_type": "fiat",
      "currency_full_name": "United State Dollars",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:54.000000Z",
      "updated_at": "2024-05-20T18:33:54.000000Z",
      "deleted_at": null,
      "can_hold_balance": 1,
      "currency_country": null
    },
    {
      "id": 2,
      "wallet": "EUR",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "€",
      "currency_name": "Euro",
      "balance_type": "fiat",
      "currency_full_name": "Euro",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:55.000000Z",
      "updated_at": "2024-06-28T15:43:01.000000Z",
      "deleted_at": null,
      "can_hold_balance": 0,
      "currency_country": null
    },
    {
      "id": 3,
      "wallet": "GBP",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "£",
      "currency_name": "British pounds",
      "balance_type": "fiat",
      "currency_full_name": "British pounds",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:56.000000Z",
      "updated_at": "2024-06-28T15:43:35.000000Z",
      "deleted_at": null,
      "can_hold_balance": 0,
      "currency_country": null
    },
    {
      "id": 4,
      "wallet": "CLP",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "CLP$",
      "currency_name": "Chilean Pesos",
      "balance_type": "fiat",
      "currency_full_name": "Chilean Pesos",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:56.000000Z",
      "updated_at": "2024-06-28T15:39:59.000000Z",
      "deleted_at": null,
      "can_hold_balance": 1,
      "currency_country": null
    },
    {
      "id": 5,
      "wallet": "PEN",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "PEN",
      "currency_name": "Peruvian sol",
      "balance_type": "fiat",
      "currency_full_name": "Peruvian sol",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:57.000000Z",
      "updated_at": "2024-05-20T18:33:57.000000Z",
      "deleted_at": null,
      "can_hold_balance": 0,
      "currency_country": null
    },
    {
      "id": 6,
      "wallet": "ARS",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "ARS$",
      "currency_name": "Argentine Peso",
      "balance_type": "fiat",
      "currency_full_name": "Argentine Peso",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:58.000000Z",
      "updated_at": "2024-06-28T15:44:19.000000Z",
      "deleted_at": null,
      "can_hold_balance": 1,
      "currency_country": null
    },
    {
      "id": 7,
      "wallet": "MXN",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "MX$",
      "currency_name": "Mexican Peso",
      "balance_type": "fiat",
      "currency_full_name": "Mexican Peso",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:59.000000Z",
      "updated_at": "2024-06-28T15:45:06.000000Z",
      "deleted_at": null,
      "can_hold_balance": 1,
      "currency_country": null
    },
    {
      "id": 8,
      "wallet": "COP",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "COL$",
      "currency_name": "Colombian Peso",
      "balance_type": "fiat",
      "currency_full_name": "Colombian Peso",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:33:59.000000Z",
      "updated_at": "2024-05-20T18:33:59.000000Z",
      "deleted_at": null,
      "can_hold_balance": 0,
      "currency_country": null
    },
    {
      "id": 9,
      "wallet": "BRL",
      "main_balance": 0,
      "ledger_balance": 0,
      "currency_icon": "R$",
      "currency_name": "Brazilian Real",
      "balance_type": "fiat",
      "currency_full_name": "Brazilian Real",
      "decimal_places": "2",
      "logo_url": "https://yativo.com/wp-content/uploads/2024/03/Yativo-42x43_090555.png",
      "created_at": "2024-05-20T18:34:00.000000Z",
      "updated_at": "2024-06-28T15:41:58.000000Z",
      "deleted_at": null,
      "can_hold_balance": 1,
      "currency_country": null
    }
  ]
}
```
