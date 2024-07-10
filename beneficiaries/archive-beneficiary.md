# Archive Beneficiary

### Archive User Beneficiary

#### Endpoint

**PUT** `{{baseUrl}}/beneficiaries/{beneficiaryID}/archive`

#### Description

This endpoint archives an existing beneficiary. The `beneficiaryID` in the URL is the ID of the beneficiary to be archived.

#### Request

**Headers**

* `Authorization: Bearer YOUR_ACCESS_TOKEN`
* `Content-Type: application/json`

**URL Parameters**

| Parameter       | Type   | Required | Description                              |
| --------------- | ------ | -------- | ---------------------------------------- |
| `beneficiaryID` | string | Yes      | The ID of the beneficiary to be archived |

**Request Body**

The request body does not require any fields for this endpoint.

**Example Request**

{% tabs %}
{% tab title="PHP" %}
```php
<?php

$beneficiary_id = "1";  // Example beneficiary ID
$api_token = "YOUR_ACCESS_TOKEN";
$base_url = "{{baseUrl}}";
$url = "$base_url/beneficiaries/$beneficiary_id/archive";

$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "PUT");
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
const beneficiary_id = "1";  // Example beneficiary ID
const api_token = "YOUR_ACCESS_TOKEN";
const base_url = "{{baseUrl}}";
const url = `${base_url}/beneficiaries/${beneficiary_id}/archive`;

fetch(url, {
    method: 'PUT',
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
curl -X PUT {{baseUrl}}/beneficiaries/1/archive \
     -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
     -H "Content-Type: application/json"

```
{% endtab %}

{% tab title="Python" %}
```python
import requests

beneficiary_id = "1"  # Example beneficiary ID
base_url = "{{baseUrl}}"
url = f"{base_url}/beneficiaries/{beneficiary_id}/archive"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json"
}

response = requests.put(url, headers=headers)
print(response.json())

```
{% endtab %}
{% endtabs %}
