# Virtual account status

### Check Virtual Account Status

#### Endpoint

**GET** `/api/v1/virtual-accounts/{account_id}/status`

#### Description

This endpoint allows you to check the status of a virtual account.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter    | Type   | Required | Description                              |
| ------------ | ------ | -------- | ---------------------------------------- |
| `account_id` | string | Yes      | Unique identifier of the virtual account |

#### Example Request

{% tabs %}
{% tab title="PHP" %}
```php
<?php

$account_id = "va_1234567890abcdef";
$api_token = "your_api_token";
$url = "{{baseUrl}}/api/v1/virtual-accounts/$account_id/status";

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

{% tab title="JavaScript " %}
```javascript
const account_id = "1234567";
const api_token = "your_api_token";
const url = `{{baseUrl}}/api/v1/virtual-accounts/${account_id}/status`;

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
```markup
curl -X GET https://api.yativo.com/api/v1/virtual-accounts/123456789ef/status \
     -H "Authorization: Bearer your_api_token" \
     -H "Content-Type: application/json"

```
{% endtab %}
{% endtabs %}

#### Response

**Success (200)**

| Field          | Type   | Description                                                       |
| -------------- | ------ | ----------------------------------------------------------------- |
| `account_id`   | string | Unique identifier of the account                                  |
| `account_name` | string | Name of the virtual account holder                                |
| `status`       | string | Current status of the account (e.g., active, inactive, suspended) |
| `created_at`   | string | Timestamp of when the account was created                         |
| `updated_at`   | string | Timestamp of the last status update                               |

**Example Response**

```
{
  "account_id": "1234533",
  "account_name": "John Doe",
  "status": "active",
  "created_at": "2024-07-10T12:34:56Z",
  "updated_at": "2024-07-11T08:45:30Z"
}

```



{% swagger src="../../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/business/virtual-account/show/{account_id}" method="get" %}
[Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}

