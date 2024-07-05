# Argentina Virtual Account

#### Create Argentina Virtual Account Documentation

**Overview**

The Create ARVirtual Account endpoint allows you to create a virtual account for a customer in Argentina. This account facilitates transactions and financial activities within the country. To create an ARVirtual account, you need to provide specific information about the customer and their documentation and the customer must be an Argentinean resident.

**Endpoint**

`POST {{baseUrl}}/customer/virtual-accounts/create`

**Request Body**

The request body should contain the following parameters:

* **customer\_id (required):** The unique identifier of the customer for whom the virtual account is being created. This identifier should be in UUID format.
* **document\_id (required):** The document ID of the customer. This can be a unique identifier assigned to the customer's official document.
* **document\_type (required):** The type of document provided. Accepted document types are "CUIT" (Clave Única de Identificación Tributaria), "CUIL" (Clave Única de Identificación Laboral), or "CDI" (Cédula de Identidad).
* **currency (required):** The currency in which the account will operate. By default, it should be set to "ARS" (Argentine Peso).

**Example Request**

```http
POST {{baseUrl}}/customer/virtual-accounts/create
Content-Type: application/json

{
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "document_id": "A23E4567",
    "document_type": "CUIT",
    "currency": "ARS"
}
```

{% tabs %}
{% tab title="PHP" %}
```
$url = "{{baseUrl}}/customer/virtual-accounts/create";
$data = array(
    "customer_id" => "123e4567-e89b-12d3-a456-426614174000",
    "document_id" => "A23E4567",
    "document_type" => "CUIT",
    "currency" => "ARS"
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

{% tab title="Python" %}
```
import requests
import json

url = "{{baseUrl}}/customer/virtual-accounts/create"
data = {
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "document_id": "A23E4567",
    "document_type": "CUIT",
    "currency": "ARS"
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
const url = "{{baseUrl}}/customer/virtual-accounts/create";
const data = {
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "document_id": "A23E4567",
    "document_type": "CUIT",
    "currency": "ARS"
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
curl -X POST {{baseUrl}}/customer/virtual-accounts/create \
-H "Content-Type: application/json" \
-H "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9" \
-d '{
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "document_id": "A23E4567",
    "document_type": "CUIT",
    "currency": "ARS"
}'

```
{% endtab %}
{% endtabs %}

**Response**

Upon successful creation of the ARVirtual account, you will receive a response with the following structure:

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

* Ensure that the provided document ID and type are accurate and valid.
* The currency parameter is required (ARS).

This documentation should guide developers on how to effectively utilize the Create Argentina Virtual Account endpoint to create virtual accounts for customers in Argentina.
