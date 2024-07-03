# Argentina Virtual Account

#### Create Argentina Virtual Account Documentation

**Overview**

The Create ARVirtual Account endpoint allows you to create a virtual account for a customer in Argentina. This account facilitates transactions and financial activities within the country. To create an ARVirtual account, you need to provide specific information about the customer and their documentation.

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
