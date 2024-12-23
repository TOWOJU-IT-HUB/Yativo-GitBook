# Virtual Account Management

### Fetch Virtual Accounts

#### Endpoint

**GET** `{{baseUrl}}`/business/virtual-account

#### Description

This endpoint allows you to fetch all virtual accounts

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`



{% swagger src="../../.gitbook/assets/Updated_Zee_v3_OpenAPI.yaml" path="/business/virtual-account" method="get" %}
[Updated_Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Updated_Zee_v3_OpenAPI.yaml)
{% endswagger %}

### Fetch Virtual Account

#### Endpoint

**POST** `{{baseUrl}}/business/virtual-account/{{customerID}}`

#### Description

This endpoint allows you to fetch a particular virtual account, effectively marking it as inactive and preventing any further transactions.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`



{% swagger src="../../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/business/virtual-account/show/{account_id}" method="get" %}
[Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}

### Delete Virtual Account

#### Endpoint

**POST** `{{baseUrl}}/business/virtual-account/delete-virtual-account/{{customerID}}`

#### Description

This endpoint allows you to delete a virtual account, effectively marking it as inactive and preventing any further transactions.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter     | Type   | Required | Description                              |
| ------------- | ------ | -------- | ---------------------------------------- |
| customer`_id` | string | Yes      | Unique identifier of the virtual account |

**Example Request**

```xml
POST {{baseUrl}}/business/virtual-account/delete-virtual-account/{{customerID}}
Authorization: Bearer your_api_token
Content-Type: application/json
```

#### Response

**Success (200)**

| Field         | Type   | Description                            |
| ------------- | ------ | -------------------------------------- |
| `message`     | string | Success message                        |
| `customer_id` | string | Unique identifier of the account       |
| `status`      | string | New status of the account ("archived") |

**Example Response**

```json
{
  "message": "Virtual account deleted successfully."
}
```



{% swagger src="../../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/business/virtual-account/delete-virtual-account/{account_id}" method="delete" %}
[Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}

### Enable Virtual Account

#### Endpoint

**POST** `{{baseUrl}}/virtual-accounts/{account_id}/enable`

#### Description

This endpoint allows you to enable a previously disabled virtual account.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter    | Type   | Required | Description                              |
| ------------ | ------ | -------- | ---------------------------------------- |
| `account_id` | string | Yes      | Unique identifier of the virtual account |

**Example Request**

```xml
POST {{baseUrl}}/virtual-accounts/1234567890/enable
Authorization: Bearer your_api_token
Content-Type: application/json

```

#### Response

**Success (200)**

| Field        | Type   | Description                           |
| ------------ | ------ | ------------------------------------- |
| `message`    | string | Success message                       |
| `account_id` | string | Unique identifier of the account      |
| `status`     | string | New status of the account ("enabled") |

**Example Response**

```json
{
  "message": "Virtual account enabled successfully.",
  "account_id": "va_1234567890abcdef",
  "status": "enabled"
}

```

{% swagger src="../../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/customer/virtual/cards/activate" method="post" %}
[Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}

### Disable Virtual Account

#### Endpoint

**POST** `{{baseUrl}}/virtual-accounts/{account_id}/disable`

#### Description

This endpoint allows you to disable a virtual account, preventing any further transactions until it is re-enabled.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter    | Type   | Required | Description                              |
| ------------ | ------ | -------- | ---------------------------------------- |
| `account_id` | string | Yes      | Unique identifier of the virtual account |

**Example Request**

```xml
POST /api/v1/virtual-accounts/va_1234567890abcdef/disable
Authorization: Bearer your_api_token
Content-Type: application/json

```

#### Response

**Success (200)**

| Field        | Type   | Description                            |
| ------------ | ------ | -------------------------------------- |
| `message`    | string | Success message                        |
| `account_id` | string | Unique identifier of the account       |
| `status`     | string | New status of the account ("disabled") |

**Example Response**

```json
{
  "message": "Virtual account disabled successfully.",
  "account_id": "va_1234567890abcdef",
  "status": "disabled"
}

```





{% tabs %}
{% tab title="PHP" %}
```
<?php

$account_id = "1234567890";
$api_token = "your_api_token";
$url = `{{baseUrl}}/virtual-accounts/$account_id/{action}`;

$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_POST, 1);
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
```javascript
const account_id = "1234567890";
const api_token = "your_api_token";
const action = "archive"; // or "enable" or "disable"
const url = `{{baseUrl}}/virtual-accounts/${account_id}/${action}`;

fetch(url, {
    method: 'POST',
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
curl -X POST https://api.yativo.com/api/v1/virtual-accounts/va_1234567890abcdef/{action} \
     -H "Authorization: Bearer your_api_token" \
     -H "Content-Type: application/json"

```
{% endtab %}
{% endtabs %}

