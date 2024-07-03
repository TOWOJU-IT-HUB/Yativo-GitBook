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
* <mark style="background-color:orange;">**Note the customer Identity Document information will not be available after this request.**</mark>

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
    "customer_name": "Test Customer",
    "customer_email": "test_customer@yativo.com",
    "customer_phone": "+19203751411",
    "customer_country": "USA",
    "customer_address": {
        "city": "Anytown",
        "state": "Anystate",
        "zipcode": "12345",
        "street": "1234 Elm Street",
        "number": "5678",
        "country": "USA"
    },
    "customer_idType": "PASSPORT",
    "customer_idNumber": "A10600011",
    "customer_idCountry": "Chile",
    "customer_idExpiration": "04/24",
    "customer_idFront": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=", // base64_encode image
    "customer_idBack": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=" // base64_encode image
}
```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "{{baseUrl}}/customer"

payload = json.dumps({
  "customer_name": "Test Customer",
  "customer_email": "test_customer@yativo.com",
  "customer_phone": "+19203751411",
  "customer_country": "USA",
  "customer_address": {
    "city": "Anytown",
    "state": "Anystate",
    "zipcode": "12345",
    "street": "1234 Elm Street",
    "number": "5678",
    "country": "USA"
  },
  "customer_idType": "PASSPORT",
  "customer_idNumber": "A10600011",
  "customer_idCountry": "Chile",
  "customer_idExpiration": "04/24",
  "customer_idFront": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=",
  "customer_idBack": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII="
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
  "customer_name": "Test Customer",
  "customer_email": "test_customer@yativo.com",
  "customer_phone": "+19203751411",
  "customer_country": "USA",
  "customer_address": {
    "city": "Anytown",
    "state": "Anystate",
    "zipcode": "12345",
    "street": "1234 Elm Street",
    "number": "5678",
    "country": "USA"
  },
  "customer_idType": "PASSPORT",
  "customer_idNumber": "A10600011",
  "customer_idCountry": "Chile",
  "customer_idExpiration": "04/24",
  "customer_idFront": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=",
  "customer_idBack": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII="
})

response = http.request(request)
puts response.read_body

```
{% endtab %}

{% tab title="NodeJs" %}
```javascript
// Some codconst axios = require('axios');
let data = JSON.stringify({
  "customer_name": "Test Customer",
  "customer_email": "test_customer@yativo.com",
  "customer_phone": "+19203751411",
  "customer_country": "USA",
  "customer_address": {
    "city": "Anytown",
    "state": "Anystate",
    "zipcode": "12345",
    "street": "1234 Elm Street",
    "number": "5678",
    "country": "USA"
  },
  "customer_idType": "PASSPORT",
  "customer_idNumber": "A10600011",
  "customer_idCountry": "Chile",
  "customer_idExpiration": "04/24",
  "customer_idFront": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=",
  "customer_idBack": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII="
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
  "customer_name": "Test Customer",
  "customer_email": "test_customer@yativo.com",
  "customer_phone": "+19203751411",
  "customer_country": "USA",
  "customer_address": {
    "city": "Anytown",
    "state": "Anystate",
    "zipcode": "12345",
    "street": "1234 Elm Street",
    "number": "5678",
    "country": "USA"
  },
  "customer_idType": "PASSPORT",
  "customer_idNumber": "A10600011",
  "customer_idCountry": "Chile",
  "customer_idExpiration": "04/24",
  "customer_idFront": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=",
  "customer_idBack": "iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII="
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
  customer_name: 'Test Customer',
  customer_email: 'test_customer@yativo.com',
  customer_phone: '+19203751411',
  customer_country: 'USA',
  customer_address: {
    city: 'Anytown',
    state: 'Anystate',
    zipcode: '12345',
    street: '1234 Elm Street',
    number: '5678',
    country: 'USA'
  },
  customer_idType: 'PASSPORT',
  customer_idNumber: 'A10600011',
  customer_idCountry: 'Chile',
  customer_idExpiration: '04/24',
  customer_idFront: 'iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII=',
  customer_idBack: 'iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mP8/wcAAgMBAZ8AItQAAAAASUVORK5CYII='
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
    "status_code": 201,
    "message": "Request successful",
    "data": {
        "customer_id": "5ae2f659-45d2-4256-9f82-2811726a5376",
        "customer_name": "Test Customer",
        "customer_email": "test_customer5@yativo.com",
        "customer_phone": "+19203751411",
        "customer_country": "USA",
        "customer_address": {
            "city": "Anytown",
            "state": "Anystate",
            "zipcode": "12345",
            "street": "1234 Elm Street",
            "number": "5678",
            "country": "USA"
        }
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
