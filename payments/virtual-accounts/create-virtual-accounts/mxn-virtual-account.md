# Mexico Virtual Account

#### Mexican Virtual Account Creation Documentation

**Overview**

This document provides guidelines for creating a virtual account for Mexican residents or non-residents with a completed and approved [KYC](../../../compliance/verification/) profile. Virtual accounts facilitate seamless financial transactions and can be tailored to specific customer needs.

**Endpoint**

`POST {{baseUrl}}`/business/virtual-account/create

**Request Body**

The request body should contain the following parameters:

* **customer\_id:** (string) The unique identifier of the customer requesting the virtual account creation.
* **currency:** (string) The currency code for the virtual account. For Mexican virtual accounts, the currency code should be "MXN".

**Example Request**

```json
{
    "customer_id": "123e4567-e89b-12d3-a456-426614174000" //optional
    "currency": "MEX"
}
```

**Response**

Upon successful virtual account creation, the server will respond with a status code of 200 and a JSON response indicating the success of the request.

* **status:** (string) A string indicating the result of the request.
* **status\_code:** (integer) A numerical code representing the HTTP status.
* **message:** (string) A descriptive message about the status of the request.

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

If there are any errors or issues with the request, the server will respond with an appropriate error status code along with a message describing the issue.

Example Error Response:

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

**Notes**

* Ensure that the provided customer ID is valid and corresponds to an existing customer.
* The document ID and document type should be accurately provided to verify the customer's identity.
* It's important to adhere to the acceptable document types specified in the documentation.

This documentation serves as a guide for developers and stakeholders involved in integrating virtual account creation functionality for Mexican residents or non-residents.
