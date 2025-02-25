# Add Beneficiary Payment Details

**To add Payment details to a beneficiary:**

## STEP 1

Make a `GET` `{{baseUrl}}/beneficiary/form/show/{{gatewayID}}`to get the _**Dynamic Form** (The form response is different for each gateway)_ for adding the beneficiary details



{% openapi src="../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/beneficiary/form/show/332" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

#### Request

**Headers**

* **Authorization:** `Bearer YOUR_ACCESS_TOKEN`
* **Content-Type:** `application/json`

**Request Example**

{% tabs %}
{% tab title="Python" %}
```python
import requests

gateway_id = "331" // example gateway ID
url = f"{{baseUrl}}/beneficiary/form/show/{gateway_id}"
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

$gateway_id = "331"; // example gateway ID
$url = "{{baseUrl}}/beneficiary/form/show/" . $gateway_id;
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
const gateway_id = "331"; //example gateway ID
const url = `{{baseUrl}}/beneficiary/form/show/${gateway_id}`;

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
```markup
curl -X GET "{{baseUrl}}/beneficiary/form/show/331" \
     -H "Authorization: Bearer YOUR_ACCESS_TOKEN"

```
{% endtab %}
{% endtabs %}



**Example response of the Dynamic Form**&#x20;

```json
{
    "nickname": "John Doe Vitawallet",
    "gateway_id": 331,
    "currency": "USD",
    "beneficiary_id": 17,
    "payment_data": {
        "beneficiary_type": "",
        "beneficiary_first_name": "",
        "beneficiary_last_name": "",
        "company_name": "",
        "beneficiary_email": "",
        "state": "",
        "city": "",
        "beneficiary_address": "",
        "zipcode": "",
        "beneficiary_document_type": "",
        "beneficiary_document_number": "",
        "account_type_bank": "",
        "account_bank": "",
        "routing_number": "",
        "purpose": "",
        "purpose_comentary": ""
    }
}
```



## STEP 2

Make a post request using the filled dynamic form as body

`POST` `{{baseUrl}}/beneficiaries/payment-methods/`&#x20;

this form Requires the **Beneficiary ID** _(gotten in the response when you_ [_Add Beneficiary_](add-beneficiary.md) _or_ [_Get Beneficiaries_](get-beneficiaries.md)_)_ to bind the payment details to the Beneficiary

#### Request

**Headers**

* **Authorization:** `Bearer YOUR_ACCESS_TOKEN`
* **Content-Type:** `application/json`



{% openapi src="../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/beneficiaries/payment-methods" method="post" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

**Request Example**

**NOTE:** _This body example matches the retrieved dynamic form from Gateway ID 331 in the above example_

```json
{
    "nickname": "John Doe Vitawallet",
    "gateway_id": 331,
    "currency": "USD",
    "beneficiary_id": 17,
    "payment_data": {
        "beneficiary_type": "Individual",
        "beneficiary_first_name": "John",
        "beneficiary_last_name": "Doe",
        "company_name": "Zee Technologies",
        "beneficiary_email": "john.doe@example.com",
        "state": "California",
        "city": "Los Angeles",
        "beneficiary_address": "123 Main St",
        "zipcode": "90001",
        "beneficiary_document_type": "DNI",
        "beneficiary_document_number": "12345678",
        "account_type_bank": "Checking",
        "account_bank": "1234567890123456",
        "routing_number": "987654321",
        "purpose": "ISGDDS",
        "purpose_comentary": "For business purposes"
    }
}

```

**Example Request**

{% tabs %}
{% tab title="Python" %}
```python
import requests
import json

url = "https://api.yourservice.com/beneficiaries/payment-methods/"
headers = {
    "Authorization": "Bearer YOUR_ACCESS_TOKEN",
    "Content-Type": "application/json"
}
data = {
    "nickname": "John Doe Vitawallet",
    "gateway_id": 331,
    "currency": "USD",
    "beneficiary_id": 17,
    "payment_data": {
        "beneficiary_type": "Individual",
        "beneficiary_first_name": "John",
        "beneficiary_last_name": "Doe",
        "company_name": "Zee Technologies",
        "beneficiary_email": "john.doe@example.com",
        "state": "California",
        "city": "Los Angeles",
        "beneficiary_address": "123 Main St",
        "zipcode": "90001",
        "beneficiary_document_type": "DNI",
        "beneficiary_document_number": "12345678",
        "account_type_bank": "Checking",
        "account_bank": "1234567890123456",
        "routing_number": "987654321",
        "purpose": "ISGDDS",
        "purpose_comentary": "For business purposes"
    }
}

response = requests.post(url, headers=headers, data=json.dumps(data))
print(response.json())

```
{% endtab %}

{% tab title="PHP" %}
```
<?php

$url = `{{baseUrl}}/beneficiaries/payment-methods/`;
$headers = array(
    "Authorization: Bearer YOUR_ACCESS_TOKEN",
    "Content-Type: application/json"
);
$data = json_encode(array(
    "nickname" => "John Doe Vitawallet",
    "gateway_id" => 331,
    "currency" => "USD",
    "beneficiary_id" => 17,
    "payment_data" => array(
        "beneficiary_type" => "Individual",
        "beneficiary_first_name" => "John",
        "beneficiary_last_name" => "Doe",
        "company_name" => "Zee Technologies",
        "beneficiary_email" => "john.doe@example.com",
        "state" => "California",
        "city" => "Los Angeles",
        "beneficiary_address" => "123 Main St",
        "zipcode" => "90001",
        "beneficiary_document_type" => "DNI",
        "beneficiary_document_number" => "12345678",
        "account_type_bank" => "Checking",
        "account_bank" => "1234567890123456",
        "routing_number" => "987654321",
        "purpose" => "ISGDDS",
        "purpose_comentary" => "For business purposes"
    )
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
const url = `{{baseUrl}}/beneficiaries/payment-methods/`

const data = {
    nickname: "John Doe Vitawallet",
    gateway_id: 331,
    currency: "USD",
    beneficiary_id: 17,
    payment_data: {
        beneficiary_type: "Individual",
        beneficiary_first_name: "John",
        beneficiary_last_name: "Doe",
        company_name: "Zee Technologies",
        beneficiary_email: "john.doe@example.com",
        state: "California",
        city: "Los Angeles",
        beneficiary_address: "123 Main St",
        zipcode: "90001",
        beneficiary_document_type: "DNI",
        beneficiary_document_number: "12345678",
        account_type_bank: "Checking",
        account_bank: "1234567890123456",
        routing_number: "987654321",
        purpose: "ISGDDS",
        purpose_comentary: "For business purposes"
    }
};

fetch(url, {
  method: 'POST',
  headers: {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(data)
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error('Error:', error));

```
{% endtab %}

{% tab title="cURL" %}
```markup
curl -X POST "{{baseUrl}}/beneficiaries/payment-methods/" \
     -H "Authorization: Bearer YOUR_ACCESS_TOKEN" \
     -H "Content-Type: application/json" \
     -d '{
           "nickname": "John Doe Vitawallet",
           "gateway_id": 331,
           "currency": "USD",
           "beneficiary_id": 17,
           "payment_data": {
               "beneficiary_type": "Individual",
               "beneficiary_first_name": "John",
               "beneficiary_last_name": "Doe",
               "company_name": "Zee Technologies",
               "beneficiary_email": "john.doe@example.com",
               "state": "California",
               "city": "Los Angeles",
               "beneficiary_address": "123 Main St",
               "zipcode": "90001",
               "beneficiary_document_type": "DNI",
               "beneficiary_document_number": "12345678",
               "account_type_bank": "Checking",
               "account_bank": "1234567890123456",
               "routing_number": "987654321",
               "purpose": "ISGDDS",
               "purpose_comentary": "For business purposes"
           }
         }'

```
{% endtab %}
{% endtabs %}
