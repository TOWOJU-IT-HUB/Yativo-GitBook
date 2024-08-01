# Transaction History

### Fetch Virtual Account Transaction History

#### Endpoint

**GET** `{{baseUrl}}/virtual-accounts/{user_id}/transactions`

#### Description

This endpoint allows you to fetch the transaction history of a virtual account.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter | Type   | Required | Description                   |
| --------- | ------ | -------- | ----------------------------- |
| `user_id` | string | Yes      | Unique identifier of the user |

**Example Request**

```
GET {{baseUrl}}/virtual-accounts/{user_id}/transactions
Authorization: Bearer your_api_token
Content-Type: application/json

```





{% tabs %}
{% tab title="PHP" %}
```
<?php

$user_id = "123456";
$api_token = "your_api_token";
$base_url = "{{baseUrl}}";
$url = "$base_url/virtual-accounts/$user_id/transactions

$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Authorization: Bearer $api_token",
    "Content-Type: application/json"
));

$response = curl_exec($ch);

if (curl_errno($ch)) {
    echo 'Error:' . curl_error($ch);
} else {
    echo $response;
}

curl_close($ch);
?>

```
{% endtab %}

{% tab title="JavaScript" %}
```
const user_id = "123456";
const api_token = "your_api_token";
const base_url = "{{baseUrl}}";
const url = `${base_url}/virtual-accounts/${user_id}/transactions

fetch(url, {
    method: 'GET',
    headers: {
        'Authorization': `Bearer ${api_token}`,
        'Content-Type': 'application/json'
    }
})
.then(response => {
    if (!response.ok) {
        throw new Error('Network response was not ok ' + response.statusText);
    }
    return response.json();
})
.then(data => console.log(data))
.catch(error => console.error('There was a problem with your fetch operation:', error));

```
{% endtab %}

{% tab title="cURL" %}
```xml
curl -X GET {{baseUrl}}/virtual-accounts/123456/transactions \
     -H "Authorization: Bearer your_api_token" \
     -H "Content-Type: application/json"

```
{% endtab %}
{% endtabs %}



### Get Individual Transaction by ID

#### Endpoint

**GET** `{{baseUrl}}/transactions/{transaction_id}`

#### Description

This endpoint allows you to fetch details of an individual transaction by its unique identifier.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter        | Type   | Required | Description                          |
| ---------------- | ------ | -------- | ------------------------------------ |
| `transaction_id` | string | Yes      | Unique identifier of the transaction |

**Example Request**



{% tabs %}
{% tab title="PHP" %}
```
<?php

$transaction_id = "txn_abcdef123456";
$api_token = "your_api_token";
$base_url = "{{baseUrl}}";
$url = "$base_url/api/v1/transactions/$transaction_id";

$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Authorization: Bearer $api_token",
    "Content-Type: application/json"
));

$response = curl_exec($ch);

if (curl_errno($ch)) {
    echo 'Error:' . curl_error($ch);
} else {
    echo $response;
}

curl_close($ch);
?>

```
{% endtab %}

{% tab title="JavaScript" %}
```
const transaction_id = "txn_abcdef123456";
const api_token = "your_api_token";
const base_url = "{{baseUrl}}";
const url = `${base_url}/transactions/${transaction_id}`;

fetch(url, {
    method: 'GET',
    headers: {
        'Authorization': `Bearer ${api_token}`,
        'Content-Type': 'application/json'
    }
})
.then(response => {
    if (!response.ok) {
        throw new Error('Network response was not ok ' + response.statusText);
    }
    return response.json();
})
.then(data => console.log(data))
.catch(error => console.error('There was a problem with your fetch operation:', error));

```
{% endtab %}

{% tab title="cURL" %}
```xml
curl -X GET {{baseUrl}}/api/v1/transactions/txn_abcdef123456 \
     -H "Authorization: Bearer your_api_token" \
     -H "Content-Type: application/json"

```
{% endtab %}
{% endtabs %}
