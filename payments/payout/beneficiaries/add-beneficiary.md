# Add Beneficiary

#### Description

This endpoint `POST` `{{baseUrl}}/beneficiaries` allows you to add a new beneficiary. The request requires a bearer token for authentication.

_**Note: To Add Payment details to the Beneficiary see**_ [_**Add beneficiary payment detail**_](add-beneficiary-payment-details.md)

#### Request Headers

* `Content-Type: application/json`
* `Authorization: Bearer <your_token>`



{% openapi src="../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/beneficiaries" method="post" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% tabs %}
{% tab title="Python" %}
```
import requests
import json

url = "{{baseUrl}}/beneficiaries"
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
headers = {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
}

response = requests.post(url, headers=headers, data=json.dumps(data))

print(response.json())

```
{% endtab %}

{% tab title="PHP" %}
```
$url = "{{baseUrl}}/beneficiaries";
$data = array(
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
);
$data_json = json_encode($data);

$headers = array(
    'Content-Type: application/json',
    'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
);

$curl = curl_init();

curl_setopt_array($curl, array(
    CURLOPT_URL => $url,
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $data_json,
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

```
{% endtab %}

{% tab title="JavaScript" %}
```
const url = "{{baseUrl}}/beneficiaries";
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
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
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
```
curl -X POST {{baseUrl}}/beneficiaries \
-H "Content-Type: application/json" \
-H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9" \
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
