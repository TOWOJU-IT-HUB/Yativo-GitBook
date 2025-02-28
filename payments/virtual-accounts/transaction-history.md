# Transaction History

### Fetch Virtual Account Transaction History

#### Endpoint

**POST** `{{baseUrl}}`/business/virtual-account/history/\{{accountNumber\}}

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
POST {{baseUrl}}/business/virtual-account/history/{{accountNumber}}
Authorization: Bearer your_api_token
Content-Type: application/json

```



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/business/virtual-account/history/{accountNumber}" method="post" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}



{% tabs %}
{% tab title="PHP" %}
```
<?php

$user_id = "123456";
$api_token = "your_api_token";
$base_url = "{{baseUrl}}";
$url = "$base_url/business/virtual-account/history/{{accountNumber}}

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
const url = `${base_url}/business/virtual-account/history/{{accountNumber}}
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
curl -X GET {{baseUrl}}/business/virtual-account/history/{{accountNumber}} \
     -H "Authorization: Bearer your_api_token" \
     -H "Content-Type: application/json"

```
{% endtab %}
{% endtabs %}



{% openapi src="broken-reference" path="/business/virtual-account/history/{accountNumber}" method="post" %}
[Broken link](broken-reference)
{% endopenapi %}
