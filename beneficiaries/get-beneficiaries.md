# Get Beneficiaries

`GET {{baseUrl}}/beneficiaries/list`

{% tabs %}
{% tab title="Python" %}
```python
import requests

url = "https://api.yativo.com/api/v1/beneficiaries/list"

payload = {}
headers = {
  'Authorization': 'Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```
{% endtab %}

{% tab title="Ruby" %}
```ruby
require "uri"
require "net/http"

url = URI("https://api.yativo.com/api/v1/beneficiaries/list")

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
  'url': 'https://api.yativo.com/api/v1/beneficiaries/list',
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

{% tab title="Response" %}
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
                "updated_at": "2024-02-06T21:07:39.000000Z"
            },
            {
                "id": 2,
                "user_id": 2,
                "nickname": "Monnet CLP (Success Tests 1)",
                "mode": "monnet",
                "currency": "CLP",
                "address": {
                    "name": "Miguel Perez",
                    "city": "Lugbe",
                    "state": "FCT - Abuja",
                    "country": "Nigeria",
                    "postal_code": "900709"
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
                "updated_at": "2024-03-02T08:54:25.000000Z"
            },
            {
                "id": 3,
                "user_id": 2,
                "nickname": "Monnet CLP (Success Tests 1)",
                "mode": "monnet",
                "currency": "CLP",
                "address": {
                    "name": "Miguel Perez",
                    "city": "Lugbe",
                    "state": "FCT - Abuja",
                    "country": "Nigeria",
                    "postal_code": "900709"
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
                "created_at": "2024-03-02T10:04:32.000000Z",
                "updated_at": "2024-03-02T10:04:32.000000Z",
            },
            {
                "id": 4,
                "user_id": 2,
                "nickname": "Monnet CLP (Success Tests 1)",
                "mode": "monnet",
                "currency": "CLP",
                "address": {
                    "name": "Miguel Perez",
                    "city": "Lugbe",
                    "state": "FCT - Abuja",
                    "country": "Nigeria",
                    "postal_code": "900709"
                },
                "beneficiary": {
                    "name": "Miguel Perez",
                    "lastName": "Perez",
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
                        "accountNumber": "2661901",
                        "cbu": null,
                        "clave": null
                    }
                },
                "created_at": "2024-03-02T10:19:37.000000Z",
                "updated_at": "2024-03-02T10:19:37.000000Z"
            },
            {
                "id": 5,
                "user_id": 2,
                "nickname": "Monnet CLP (Success Tests 2)",
                "mode": "monnet",
                "currency": "CLP",
                "address": {
                    "name": "Miguel Perez",
                    "city": "Lugbe",
                    "state": "FCT - Abuja",
                    "country": "Nigeria",
                    "postal_code": "900709"
                },
                "beneficiary": {
                    "name": "Miguel Perez",
                    "lastName": "Perez",
                    "email": "john@yativo.com",
                    "document": {
                        "type": 1,
                        "number": "0366311-3"
                    }
                },
                "payment_object": {
                    "bankAccount": {
                        "bankCode": "001",
                        "accountType": 4,
                        "accountNumber": "2661901",
                        "cbu": null,
                        "clave": null
                    }
                },
                "created_at": "2024-03-02T11:24:24.000000Z",
                "updated_at": "2024-03-02T11:24:24.000000Z"
            },
            {
                "id": 6,
                "user_id": 2,
                "nickname": "Monnet CLP (Success Tests 2)",
                "mode": "monnet",
                "currency": "CLP",
                "address": {
                    "name": "Miguel Perez",
                    "city": "Lugbe",
                    "state": "FCT - Abuja",
                    "country": "Nigeria",
                    "postal_code": "900709"
                },
                "beneficiary": {
                    "name": "Miguel Perez",
                    "lastName": "Perez",
                    "email": "john@yativo.com",
                    "document": {
                        "type": 1,
                        "number": "0366311-3"
                    }
                },
                "payment_object": {
                    "bankAccount": {
                        "bankCode": "001",
                        "accountType": 4,
                        "accountNumber": "2661901",
                        "cbu": null,
                        "clave": null
                    }
                },
                "created_at": "2024-03-02T11:37:41.000000Z",
                "updated_at": "2024-03-02T11:37:41.000000Z"
            },
            {
                "id": 7,
                "user_id": 2,
                "nickname": "Monnet CLP (Success Tests 2)",
                "mode": "monnet",
                "currency": "CLP",
                "address": {
                    "name": "Miguel Perez",
                    "city": "Lugbe",
                    "state": "FCT - Abuja",
                    "country": "Nigeria",
                    "postal_code": "900709"
                },
                "beneficiary": {
                    "name": "Miguel Perez",
                    "lastName": "Perez",
                    "email": "john@yativo.com",
                    "document": {
                        "type": 1,
                        "number": "0366311-3"
                    }
                },
                "payment_object": {
                    "bankAccount": {
                        "bankCode": "001",
                        "accountType": 4,
                        "accountNumber": null,
                        "cbu": null,
                        "clave": null
                    }
                },
                "created_at": "2024-03-02T11:38:53.000000Z",
                "updated_at": "2024-03-02T11:38:53.000000Z"
            }
        ],
        "first_page_url": "https://api.yativo.com/api/v1/beneficiaries?page=1",
        "from": 1,
        "last_page": 1,
        "last_page_url": "https://api.yativo.com/api/v1/beneficiaries?page=1",
        "links": [
            {
                "url": null,
                "label": "&laquo; Previous",
                "active": false
            },
            {
                "url": "https://api.yativo.com/api/v1/beneficiaries?page=1",
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
        "path": "https://api.yativo.com/api/v1/beneficiaries",
        "per_page": 20,
        "prev_page_url": null,
        "to": 7,
        "total": 7
    }
}
```
{% endtab %}
{% endtabs %}
