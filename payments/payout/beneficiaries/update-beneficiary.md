# Update Beneficiary

#### Endpoint

`PUT {{baseUrl}}/beneficiaries/{beneficiaryID}`

#### Description

This endpoint updates the details of an existing beneficiary. The `beneficiaryID` in the URL is the ID of the beneficiary to be updated, which is included in the beneficiary object.

#### Request

**Headers**

* **Authorization:** `Bearer YOUR_ACCESS_TOKEN`
* **Content-Type:** `application/json`

**URL Parameters**

* **beneficiaryID:** The ID of the beneficiary to be updated.



{% openapi src="../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/beneficiaries/6" method="put" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

**Request Body**

The request body should contain the fields to be updated. Here is an example of the request body with all the fields that can be updated:

```json
{
    "recipient_type": "individual",
    "customer_name": "John Smith",
    "customer_email": "john@yativo.com",
    "country": "Chile",
    "customer_address": {
        "address_line_1": "1st episode john doe street",
        "address_line_2": "this can be null",
        "city": "Santiago",
        "county": "Chile",
        "postal_code": 900901
    }
}

```

#### Response

**Example Success Response**

```json
{
  "status": "success",
  "status_code": 200,
  "message": "Beneficiary updated successfully",
  "data": {
    "id": 1,
    "user_id": 2,
    "nickname": "John Doe Zenith bank",
    "mode": "unknown",
    "currency": "NGN",
    "address": {
      "city": "Lugbe",
      "state": "FCT - Abuja",
      "country": "Nigeria",
      "postal_code": "900709"
    },
    "beneficiary": {
      "name": "Yativo Smith",
      "email": "john@yativo.com"
    },
    "payment_object": {
      "bank_name": "Access bank",
      "bank_code": "044",
      "account_number": "0719841763",
      "account_name": "Yativo Smith"
    },
    "created_at": "2024-02-06T21:07:39.000000Z",
    "updated_at": "2024-02-06T21:07:39.000000Z",
    "deleted_at": null
  }
}

```



**Request example**

{% tabs %}
{% tab title="Python" %}
```python
import requests
import json

beneficiary_id = "1"  # Example beneficiary ID
url = f"https://api.yourservice.com/beneficiaries/{beneficiary_id}"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json"
}
data = {
    "recipient_type": "individual",
    "customer_name": "John Smith",
    "customer_email": "john@yativo.com",
    "country": "Nigeria",
    "customer_address": {
        "address_line_1": "1st episode john doe street",
        "address_line_2": "this can be null",
        "city": "Ikeja",
        "county": "Lagos",
        "postal_code": 900901
    }
}

response = requests.put(url, headers=headers, data=json.dumps(data))
print(response.json())

```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

$beneficiary_id = "1";  // Example beneficiary ID
$url = "https://api.yourservice.com/beneficiaries/" . $beneficiary_id;
$headers = array(
    "Authorization: Bearer YOUR_ACCESS_TOKEN",
    "Content-Type: application/json"
);
$data = json_encode(array(
    "recipient_type" => "individual",
    "customer_name" => "John Smith",
    "customer_email" => "john@yativo.com",
    "country" => "Nigeria",
    "customer_address" => array(
        "address_line_1" => "1st episode john doe street",
        "address_line_2" => "this can be null",
        "city" => "Ikeja",
        "county" => "Lagos",
        "postal_code" => 900901
    )
));

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => $url,
    CURLOPT_RETURNTRANSFER => true,
    CURLOPT_HTTPHEADER => $headers,
    CURLOPT_CUSTOMREQUEST => "PUT",
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
const beneficiary_id = "1"; // Example beneficiary ID
const url = `https://api.yourservice.com/beneficiaries/${beneficiary_id}`;

const data = {
  "recipient_type": "individual",
  "customer_name": "John Smith",
  "customer_email": "john@yativo.com",
  "country": "Nigeria",
  "customer_address": {
    "address_line_1": "1st episode john doe street",
    "address_line_2": "this can be null",
    "city": "Ikeja",
    "county": "Lagos",
    "postal_code": 900901
  }
};

const options = {
  method: 'PUT',
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

{% tab title="cURL" %}
```xml
curl -X PUT "https://api.yourservice.com/beneficiaries/1" \
     -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
     -H "Content-Type: application/json" \
     -d '{
           "recipient_type": "individual",
           "customer_name": "John Smith",
           "customer_email": "john@yativo.com",
           "country": "Nigeria",
           "customer_address": {
               "address_line_1": "1st episode john doe street",
               "address_line_2": "this can be null",
               "city": "Ikeja",
               "county": "Lagos",
               "postal_code": 900901
           }
         }'

```
{% endtab %}
{% endtabs %}
