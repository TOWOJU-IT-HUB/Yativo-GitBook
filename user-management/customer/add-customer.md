---
description: >-
  The "Add Customer" endpoint is a vital component of our API, designed to
  facilitate the creation and storage of new customer records within the system.
---

# Add Customer

The <mark style="color:green;">`POST`</mark> `{{baseUrl}}/customer`  endpoint is designed to facilitate the creation and storage of new customer records within the system. This endpoint allows applications to efficiently add customer data, ensuring that new customer information is accurately recorded for subsequent use. It supports various use cases, including registering new users, onboarding clients, and integrating customer data from other systems.

**Key Features:**

* **HTTP Method**: `POST`
* **Endpoint URL**: \{{baseUrl\}}`/customer`
* **Authentication**: Requires Bearer token to ensure secure access.
* **Request Payload**: Accepts a JSON object containing detailed customer information, such as name, email, phone number, address, and identification details.
* <mark style="background-color:orange;">**Note the customer KYC can be carried out by the user via link sent to the user email or you can send the information via API.**</mark>

## Create a new user

<mark style="color:green;">`POST`</mark> `/customer`

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

{% tabs %}
{% tab title="Request body" %}
```json
{
    "customer_name": "Emmanuel A Towoju",
    "customer_email": "tbash7676@gmail.com",
    "customer_phone": "+2349039395114",
    "customer_country": "USA",
    "customer_type": "individual", // or business, defaults to individual when not passed
    "send_kyc_mail": true // default to true. email with URL to complete kyc will be sent to custome_email
}
```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "{{baseUrl}}/customer"

payload = json.dumps({
    "customer_name": "Emmanuel A Towoju",
    "customer_email": "tbash7676@gmail.com",
    "customer_phone": "+2349039395114",
    "customer_country": "USA",
    "customer_type": "individual", // or business, defaults to individual when not passed
    "send_kyc_mail": true // default to true. email with URL to complete kyc will be sent to custome_email
})
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)

```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require "uri"
require "json"
require "net/http"

url = URI("{{baseUrl}}/customer")

http = Net::HTTP.new(url.host, url.port);
request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
request.body = JSON.dump({
    "customer_name": "Emmanuel A Towoju",
    "customer_email": "tbash7676@gmail.com",
    "customer_phone": "+2349039395114",
    "customer_country": "USA",
    "customer_type": "individual", // or business, defaults to individual when not passed
    "send_kyc_mail": true // default to true. email with URL to complete kyc will be sent to custome_email
})

response = http.request(request)
puts response.read_body

```
{% endtab %}

{% tab title="NodeJs" %}
```javascript
// Some codconst axios = require('axios');
let data = JSON.stringify({
    "customer_name": "Emmanuel A Towoju",
    "customer_email": "tbash7676@gmail.com",
    "customer_phone": "+2349039395114",
    "customer_country": "USA",
    "customer_type": "individual", // or business, defaults to individual when not passed
    "send_kyc_mail": true // default to true. email with URL to complete kyc will be sent to custome_email
});

let config = {
  method: 'post',
  maxBodyLength: Infinity,
  url: '{{baseUrl}}/customer',
  headers: { 
    'Content-Type': 'application/json', 
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  },
  data : data
};

axios.request(config)
.then((response) => {
  console.log(JSON.stringify(response.data));
})
.catch((error) => {
  console.lo<?php
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php

$client = new Client();
$headers = [
  'Content-Type' => 'application/json',
  'Authorization' => 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
];
$body = '{
    "customer_name": "Emmanuel A Towoju",
    "customer_email": "tbash7676@gmail.com",
    "customer_phone": "+2349039395114",
    "customer_country": "USA",
    "customer_type": "individual", // or business, defaults to individual when not passed
    "send_kyc_mail": true // default to true. email with URL to complete kyc will be sent to custome_email
}';
$request = new Request('POST', '{{baseUrl}}/customer', $headers, $body);
$res = $client->sendAsync($request)->wait();
echo $res->getBody();

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
const url = '{{baseUrl}}/customer';

const payload = JSON.stringify({
    "customer_name": "Emmanuel A Towoju",
    "customer_email": "tbash7676@gmail.com",
    "customer_phone": "+2349039395114",
    "customer_country": "USA",
    "customer_type": "individual", // or business, defaults to individual when not passed
    "send_kyc_mail": true // default to true. email with URL to complete kyc will be sent to custome_email
});

const options = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  },
  body: payload
};

fetch(url, options)
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok ' + response.statusText);
    }
    return response.json();
  })
  .then(data => console.log('Customer created:', data))
  .catch(error => console.error('Error:', error));

```
{% endtab %}
{% endtabs %}

**Response**

{% tabs %}
{% tab title="201" %}
```json
{
  "status": "success",
  "status_code": 200,
  "message": "Customer created successfully",
  "data": {
    "id": "21fe7601-3be3-4d15-94c0-a94b15d8b872",
    "full_name": "Emmanuel A Towoju",
    "email": "perfectwordpre@gmail.com",
    "type": "individual",
    "kyc_link": "https://bridge.withpersona.com/verify?inquiry-template-id=itmpl_NtHYpb9AbEYCPxGo5iRbc9d2&fields[developer_id]=2da859f2-9764-48e6-92e6-dd9f6747801b&fields[iqt_token]=46f7565fe2ba42843b957cec6d783e48f85dff6d6ea56cf5753634b09a3214e8WwzmNl&reference-id=7d5b9315-796e-4d4d-b771-1ee5997e4abf&redirect-uri=https%3A%2F%2Fyativo-web-design-nine.vercel.app%2F&environment-id=env_UWeuo2CnqFQXVeKujbQLBx6u",
    "tos_link": "https://dashboard.bridge.xyz/accept-terms-of-service?customer_id=7d5b9315-796e-4d4d-b771-1ee5997e4abf",
    "kyc_status": "approved",
    "rejection_reasons": [],
    "tos_status": "pending",
    "created_at": "2024-12-01T18:46:15.392Z",
    "customer_id": "7d5b9315-796e-4d4d-b771-1ee5997e4abf",
    "persona_inquiry_type": "gov_id_db"
  }
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}



