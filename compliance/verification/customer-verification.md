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

<table data-full-width="true"><thead><tr><th>Parameter</th><th>Type</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>first_name</code></td><td>string</td><td>Yes</td><td>The customer's first name.</td></tr><tr><td><code>last_name</code></td><td>string</td><td>Yes</td><td>The customer's last name.</td></tr><tr><td><code>middle_name</code></td><td>string</td><td>No</td><td>The customer's middle name.</td></tr><tr><td><code>email</code></td><td>string</td><td>No</td><td>The customer's email address.</td></tr><tr><td><code>phone</code></td><td>string</td><td>No</td><td>The customer's phone number.</td></tr><tr><td><code>date_of_birth</code> / <code>birth_date</code></td><td>string</td><td>Yes</td><td>The customer's date of birth (YYYY-MM-DD).</td></tr><tr><td><code>ip_address</code></td><td>string</td><td>No</td><td>The customer's IP address.</td></tr><tr><td><code>type</code></td><td>string</td><td>Yes</td><td>The type of customer (e.g., "individual").</td></tr><tr><td><code>address.street_line_1</code></td><td>string</td><td>Yes</td><td>The first line of the customer's address.</td></tr><tr><td><code>address.city</code></td><td>string</td><td>Yes</td><td>The city of the customer's address.</td></tr><tr><td><code>address.state</code></td><td>string</td><td>No*</td><td>The state/province (ISO 3166-2 code). Required if the country has subdivisions.</td></tr><tr><td><code>address.postal_code</code></td><td>string</td><td>Yes</td><td>The postal/ZIP code of the customer's address.</td></tr><tr><td><code>address.country</code></td><td>string (ISO 3166-1)</td><td>Yes</td><td>The country code (e.g., "USA" for America, "NGA" for Nigeria).</td></tr><tr><td><code>nationality</code></td><td>string (ISO 3166-1)</td><td>Yes</td><td>The customer's nationality (e.g., "USA", "NGA").</td></tr><tr><td><code>employment_status</code></td><td>string</td><td>Yes</td><td>The customer's employment status (e.g., "employed", "self_employed", "unemployed").</td></tr><tr><td><code>expected_monthly_payments</code></td><td>string (range)</td><td>Yes</td><td>Expected monthly payments (e.g., "5000_9999").</td></tr><tr><td><code>acting_as_intermediary</code></td><td>string ("yes" / "no")</td><td>Yes</td><td>Whether the customer is acting as an intermediary.</td></tr><tr><td><code>most_recent_occupation</code></td><td>string (code)</td><td>Yes</td><td>The customer's most recent occupation (use an API endpoint for supported codes).</td></tr><tr><td><code>account_purpose</code></td><td>string</td><td>Yes</td><td>The purpose of the account (e.g., "purchase_goods_and_services").</td></tr><tr><td><code>account_purpose_other</code></td><td>string / null</td><td>No</td><td>Required if <code>account_purpose</code> includes "other".</td></tr><tr><td><code>source_of_funds</code></td><td>string</td><td>Yes</td><td>Source of funds (e.g., "salary", "savings", "investments_loans").</td></tr><tr><td><code>identifying_information</code></td><td>array of objects</td><td>Yes*</td><td>Required if customer is from the USA. Contains identity details.</td></tr><tr><td><code>identifying_information[].type</code></td><td>string</td><td>Yes</td><td>The type of identification (e.g., "ssn", "drivers_license").</td></tr><tr><td><code>identifying_information[].issuing_country</code></td><td>string (ISO 3166-1)</td><td>Yes</td><td>The issuing country for the ID.</td></tr><tr><td><code>identifying_information[].number</code></td><td>string</td><td>Yes</td><td>The identification number.</td></tr><tr><td><code>identifying_information[].image_front</code></td><td>string (Base64)</td><td>No</td><td>Base64-encoded image of the front of the document (if applicable).</td></tr><tr><td><code>identifying_information[].image_back</code></td><td>string (Base64)</td><td>No</td><td>Base64-encoded image of the back of the document (if applicable).</td></tr><tr><td><code>documents</code></td><td>array of objects</td><td>No</td><td>Additional documentation provided.</td></tr><tr><td><code>documents[].purposes</code></td><td>array of strings</td><td>Yes</td><td>The purpose of the document (e.g., "proof_of_address").</td></tr><tr><td><code>documents[].file</code></td><td>string (Base64)</td><td>Yes</td><td>Base64-encoded document file.</td></tr></tbody></table>

{% code fullWidth="true" %}
```json
{
    "type": "individual",
    "first_name": "John",
    "last_name": "Doe",
    "email": "email@example.com",
    "address": {
        "street_line_1": "123 Main St",
        "city": "New York City",
        "state": "FC", // ISO 3166-2 subdivision code. Must be supplied if the country has subdivisions.
        "postal_code": "10001",
        "country": "USA" // ISO 3166-1. Example: USA - America, NGA - Nigeria
    },
    "nationality": "USA", // ISO 3166-1. Example: USA, NGA
    "birth_date": "2007-01-01",
    "employment_status": "employed", // employed, homemaker, retired, self_employed, student, unemployed
    "expected_monthly_payments": "5000_9999", // 0_4999, 5000_9999, 10000_49999, 50000_plus
    "acting_as_intermediary": "no",
    "most_recent_occupation": "291291", // call the endpoint for list of supported codes
    "account_purpose": "purchase_goods_and_services", // charitable_donations, investment_purposes, other, payments_to_friends_or_family_abroad, personal_or_living_expenses, protect_wealth, purchase_goods_and_services, receive_payment_for_freelancing, receive_salary, ecommerce_retail_payments, investment_purposes
    "account_purpose_other": null, // Required if account_purpose includes other.
    "source_of_funds": "salary",  // salary,savings,investments_loans,inheritance,sale_of_assets_real_estate,pension_retirement,gifts,government_benefits,gambling_proceeds,someone_elses_funds,company_funds,amazon_ecommerce_reseller
    "identifying_information": [
        {
            "type": "ssn", // required if customer is from USA
            "issuing_country": "usa",
            "number": "xxx-xx-xxxx"
        },
        {
            "type": "drivers_license",
            "issuing_country": "usa",
            "number": "xxxxxxxxxxxxx",
            "image_front": "data:image/jpg;base64,...",
            "image_back": "data:image/jpg;base64,..."
        }
    ],
    "documents": [ // Additional documentation.
        {
            "purposes": [
                "proof_of_address"
            ],
            "file": "data:image/jpg;base64,..."
        }
    ]
}
```
{% endcode %}

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



