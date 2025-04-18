# USD Virtual Account

#### Create USD Virtual Account Documentation

**Overview**

The Create Virtual Account endpoint allows you to create a virtual account for a customer with complete and approved [KYC](../../../compliance/verification/) profile. This account enables your customer to receive USD deposits via ACH or FEDWIRE. Third party deposits are also supported, but we may ask for more information. To create a USD Virtual account, you need to provide the Customer ID and currency to USD in the POST Request.

**Endpoint**

`POST {{baseUrl}}`/business/virtual-account/create

**Request Body**

The request body should contain the following parameters:

* **customer\_id (required):** The unique identifier of the customer for whom the virtual account is being created. This identifier should be in UUID format.
* **currency (required):** The currency in which the account will operate.  It should be set to "USD" (United States Dollars).

**Example Request**

```http
POST {{baseUrl}}/business/virtual-account/create
Content-Type: application/json

{
    "customer_id": "123e4567-e89b-12d3-a456-426614174000", //optional
    "currency": "USD"
}
```

{% tabs %}
{% tab title="PHP" %}
```
$url = "{{baseUrl}}/business/virtual-account/create";
$data = array(
    "customer_id" => "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxx",
    "currency" => "USD"
);
$data_json = json_encode($data);

$headers = array(
    'Content-Type: application/json',
    'Authorization: Bearer eyJ0xxxxxxxxxxxxxxxxx'
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

{% tab title="Python" %}
```
import requests
import json

url = "{{baseUrl}}/business/virtual-account/create"
data = {
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "currency": "USD"
}
headers = {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
}

response = requests.post(url, headers=headers, data=json.dumps(data))

print(response.text)

```
{% endtab %}

{% tab title="JavaScript" %}
```
const url = "{{baseUrl}}/business/virtual-account/create?customer_id={{customerID}}";
const data = {
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "currency": "USD"
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
curl -X POST {{baseUrl}}/business/virtual-account/create?customer_id={{customerID}}\
-H "Content-Type: application/json" \
-H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9" \
-d '{
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "currency": "USD"
}'

```
{% endtab %}
{% endtabs %}

**Response**

Upon successful creation of the USD Virtual account, you will receive a response with the following structure:

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "message": "Virtual account creation in progress"
    }
}
```

**Error Handling**

In case of errors, the response will include an appropriate status code and an error message detailing the issue.

**Example Error Response**

```json
{
    "status": "error",
    "status_code": 400,
    "message": "Request failed",
    "data" : {
        "message": "Invalid document type provided"
    }
}
```

**Additional Notes**

* The currency parameter is required (USD).

