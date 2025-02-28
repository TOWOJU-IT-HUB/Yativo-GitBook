# Virtual Account Management

### Fetch Virtual Accounts

#### Endpoint

**GET** `{{baseUrl}}`/business/virtual-account

#### Description

This endpoint allows you to fetch all virtual accounts

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/business/virtual-account" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% openapi src="broken-reference" path="/business/virtual-account" method="get" %}
[Broken link](broken-reference)
{% endopenapi %}

### Fetch Virtual Account

#### Endpoint

**POST** `{{baseUrl}}/business/virtual-account/show/{{customerID}}`

#### Description

This endpoint allows you to fetch a particular virtual account, effectively marking it as inactive and preventing any further transactions.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/business/virtual-account/show/e7ee01e9-adb8-4431-903d-b89d0872320d" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% openapi src="broken-reference" path="/business/virtual-account/show/{account_id}" method="get" %}
[Broken link](broken-reference)
{% endopenapi %}

### Delete Virtual Account

#### Endpoint

**POST** `{{baseUrl}}/business/virtual-account/delete-virtual-account/{{customerID}}`

#### Description

This endpoint allows you to delete a virtual account, effectively marking it as inactive and preventing any further transactions.

#### Request

**Headers**

* `Content-Type: application/json`
* `Authorization: Bearer {your_api_token}`

**Path Parameters**

| Parameter     | Type   | Required | Description                              |
| ------------- | ------ | -------- | ---------------------------------------- |
| customer`_id` | string | Yes      | Unique identifier of the virtual account |

**Example Request**

```xml
POST {{baseUrl}}/business/virtual-account/delete-virtual-account/{{customerID}}
Authorization: Bearer your_api_token
Content-Type: application/json
```

#### Response

**Success (200)**

| Field         | Type   | Description                            |
| ------------- | ------ | -------------------------------------- |
| `message`     | string | Success message                        |
| `customer_id` | string | Unique identifier of the account       |
| `status`      | string | New status of the account ("archived") |

**Example Response**

```json
{
  "message": "Virtual account deleted successfully."
}
```



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/business/virtual-account/delete-virtual-account/e7ee01e9-adb8-4431-903d-b89d0872320d" method="delete" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% openapi src="broken-reference" path="/business/virtual-account/delete-virtual-account/{account_id}" method="delete" %}
[Broken link](broken-reference)
{% endopenapi %}

{% openapi src="broken-reference" path="/customer/virtual/cards/activate" method="post" %}
[Broken link](broken-reference)
{% endopenapi %}





