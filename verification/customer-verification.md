# Customer Verification

#### 1. Introduction

The Yativo Business API provides a robust solution for verifying the identity of your end-users/customers. This API allows businesses to ensure compliance with KYC (Know Your Customer) regulations by validating user information in real-time.

#### 2. Authentication

All API requests must be authenticated using an API key. You can obtain your API key from the Yativo Business API dashboard. Include this key in the header of your requests as follows:

```
Authorization: Bearer YOUR_API_KEY
```

#### 3. Endpoints

**Verify Customer**

* **Endpoint:** `POST {{baseUrl}}/verification/verify-customer`
* **Description:** Verify the identity of a customer.
* **Headers:**
  * `Authorization: Bearer YOUR_API_KEY`
  * `Content-Type: application/json`

**Request Parameters:**

| Parameter       | Type   | Required | Description                                |
| --------------- | ------ | -------- | ------------------------------------------ |
| `first_name`    | string | Yes      | The customer's first name.                 |
| `last_name`     | string | Yes      | The customer's last name.                  |
| `middle_name`   | string | No       | The customer's middle name.                |
| `email`         | string | No       | The customer's email address.              |
| `phone`         | string | No       | The customer's phone number.               |
| `date_of_birth` | string | Yes      | The customer's date of birth (YYYY-MM-DD). |
| `ip_address`    | string | No       | The customer's IP address.                 |

```
//Example request
{
    "first_name": "John",
    "last_name": "Doe",
    "middle_name": "A",
    "email": "john.doe@example.com",
    "phone": "+1234567890",
    "date_of_birth": "1990-01-01",
    "ip_address": "192.168.1.1"
}

```

#### 4. Error Codes

The API uses standard HTTP status codes to indicate the success or failure of an API request. The following table provides details of common error codes:

| Status Code | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| 200         | Request was successful.                                     |
| 400         | Bad request. The request parameters are invalid or missing. |
| 401         | Unauthorized. The API key is missing or invalid.            |
| 403         | Forbidden. You do not have access to this resource.         |
| 404         | Not found. The requested resource could not be found.       |
| 500         | Internal server error. An error occurred on the server.     |

#### 5. Best Practices

* **Secure Your API Key:** Never expose your API key in public repositories or client-side code.
* **Validate Input:** Ensure all required fields are provided and valid before making API requests.
* **Handle Errors Gracefully:** Implement error handling in your application to manage different HTTP status codes and error responses.
* **Rate Limiting:** Be mindful of the API rate limits and avoid making excessive requests in a short period.
