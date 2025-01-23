# Customer Verification

#### 1. Introduction

The Yativo Business API provides a robust solution for verifying the identity of your end-users/customers. This API allows businesses to ensure compliance with KYC (Know Your Customer) regulations by validating user information in real-time.

The KYC can be completed via API or a verification link will be sent to the End-user/customer via email.

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

<table><thead><tr><th width="189">Parameter</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>first_name</code></td><td>string</td><td>Yes</td><td>The customer's first name.</td></tr><tr><td><code>last_name</code></td><td>string</td><td>Yes</td><td>The customer's last name.</td></tr><tr><td><code>middle_name</code></td><td>string</td><td>No</td><td>The customer's middle name.</td></tr><tr><td><code>email</code></td><td>string</td><td>No</td><td>The customer's email address.</td></tr><tr><td><code>phone</code></td><td>string</td><td>No</td><td>The customer's phone number.</td></tr><tr><td><code>date_of_birth</code></td><td>string</td><td>Yes</td><td>The customer's date of birth (YYYY-MM-DD).</td></tr><tr><td><code>ip_address</code></td><td>string</td><td>No</td><td>The customer's IP address.</td></tr></tbody></table>

```json
//Example request
{
    "first_name": "John",
    "customer_id": "f66b8549-97a9-48f4-aee7-e546e4859ad8",
    "last_name": "Doe",
    "middle_name": "Smith",
    "email": "john.doe@example.com",
    "phone": "+1234567890",
    "dob": "1980-01-01",
    "longitude":  "99.90",
    "latitude": "34.533",
    "gender": "Male",
    "mobile": "+1234567890",
    "street": "123 Main Street",
    "landmark": "Near City Park",
    "lga": "Central Business District",
    "state": "TX", // ISO 3166-2 subdivision code. Must be supplied if the country has subdivisions.
    "postal_code": "90011",
    "country": "USA", // Three-letter alpha-3 country code as defined in the ISO 3166-1 spec.
    "date_of_birth": "1980-01-01",
    "ip_address": "192.168.1.1",
    "idNumber": "A10200086",
    "selfieimage": "https://alphamead.lon1.digitaloceanspaces.com/1fa13101-7aad-4c0b-a3ae-4d85bf2b2864/6737740256106_JPEG_20241115_171650_7855778370240702059.jpg",
    "photoidimage": "https://alphamead.lon1.digitaloceanspaces.com/1fa13101-7aad-4c0b-a3ae-4d85bf2b2864/6737740256106_JPEG_20241115_171650_7855778370240702059.jpg",
    "imageFrontSide": "https://alphamead.lon1.digitaloceanspaces.com/1fa13101-7aad-4c0b-a3ae-4d85bf2b2864/6737740256106_JPEG_20241115_171650_7855778370240702059.jpg",
    "imageBackSide": "https://alphamead.lon1.digitaloceanspaces.com/1fa13101-7aad-4c0b-a3ae-4d85bf2b2864/6737740256106_JPEG_20241115_171650_7855778370240702059.jpg",
    "proof_of_address_document": "https://alphamead.lon1.digitaloceanspaces.com/1fa13101-7aad-4c0b-a3ae-4d85bf2b2864/6737740256106_JPEG_20241115_171650_7855778370240702059.jpg",
    "tax_identification_number": "75-1234567",
    "employment_status": "employed",
    "expected_monthly_payments": "xoxo",
    "most_recent_occupation": "xoxo",
    "primary_purpose": "xoxo",
    "primary_purpose_other": "xoxo",
    "source_of_funds": "xoxo",
    "gov_id_country": "xoxo",
    "gov_id_type": "xoxo"
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



{% swagger src="../../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/verification/verify-customer" method="post" %}
[Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}
