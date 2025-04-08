# Get Beneficiaries

`GET {{baseUrl}}/beneficiaries/list`

#### Description

This endpoint retrieves a list of beneficiaries associated with the authenticated user. Beneficiaries are the recipients of payments or transfers, and their details are stored in the system for ease of transactions.

#### Request

**Headers**

* **Authorization:** `Bearer YOUR_ACCESS_TOKEN`



{% openapi src="../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/beneficiaries/list" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

**Request Body**

No request body is required for this endpoint.

{% tabs %}
{% tab title="Python" %}
```python
import requests

url = "{{baseUrl}}/beneficiaries/list"

payload = {}
headers = {
  'Authorization': 'Bearer eyJ0exxxxxxxxxxxxxxxxxxxx'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require "uri"
require "net/http"

url = URI("{{baseUrl}}/beneficiaries/list")

https = Net::HTTP.new(url.host, url.port)
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Authorization"] = "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"

response = https.request(request)
puts response.read_body

```
{% endtab %}

{% tab title="Node js" %}
```ejs
var request = require('request');
var options = {
  'method': 'GET',
  'url': '{{baseUrl}}/beneficiaries/list',
  'headers': {
    'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```
{% endtab %}
{% endtabs %}

#### Response

**Example Response**

```json
{
  "status": "success",
  "status_code": 200,
  "message": "Request successful",
  "data": {
    "current_page": 1,
    "data": [
      {
        "id": 1,
        "user_id": 2,
        "nickname": "John Doe Banco de Chile",
        "mode": "unknown",
        "currency": "CLP",
        "address": {
          "city": "Santiago",
          "state": "Región Metropolitana",
          "country": "Chile",
          "postal_code": "8320000"
        },
        "beneficiary": {
          "name": "Yativo Smith",
          "email": "john@yativo.com"
        },
        "payment_object": {
          "bank_name": "Banco de Chile",
          "bank_code": "001",
          "account_number": "0719841763",
          "account_name": "Yativo Smith"
        },
        "created_at": "2024-02-06T21:07:39.000000Z",
        "updated_at": "2024-02-06T21:07:39.000000Z",
        "deleted_at": null
      },
      {
        "id": 2,
        "user_id": 2,
        "nickname": "Monnet CLP (Success Tests 1)",
        "mode": "monnet",
        "currency": "CLP",
        "address": {
          "city": "Santiago",
          "state": "Región Metropolitana",
          "country": "Chile",
          "postal_code": "8320000"
        },
        "beneficiary": {
          "name": "Miguel Perez",
          "email": "john@yativo.com",
          "document": {
            "type": 1,
            "number": "10366311-3"
          }
        },
        "payment_object": {
          "bankAccount": {
            "bankCode": "001",
            "accountType": 1,
            "accountNumber": "2661901"
          }
        },
        "created_at": "2024-03-02T08:54:25.000000Z",
        "updated_at": "2024-03-02T08:54:25.000000Z",
        "deleted_at": null
      }
    ],
    "first_page_url": "https://zee.test/api/v1/beneficiaries?page=1",
    "from": 1,
    "last_page": 1,
    "last_page_url": "https://zee.test/api/v1/beneficiaries?page=1",
    "links": [
      {
        "url": null,
        "label": "&laquo; Previous",
        "active": false
      },
      {
        "url": "https://zee.test/api/v1/beneficiaries?page=1",
        "label": "1",
        "active": true
      },
      {
        "url": null,
        "label": "Next &raquo;",
        "active": false
      }
    ],
    "next_page_url": null,
    "path": "https://zee.test/api/v1/beneficiaries",
    "per_page": 20,
    "prev_page_url": null,
    "to": 7,
    "total": 7
  }
}
```
