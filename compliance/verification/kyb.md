---
description: Verification for your Business Customers
---

# KYB

**Know Your Business (KYB) Verification**

***

### 1. Introduction

The Yativo Business API provides a robust solution for verifying the identity of businesses. This API enables businesses to ensure compliance with KYB (Know Your Business) regulations by validating company details.

**For Individual Customers refer to** [**KYC**](kyc.md)**.**&#x20;

The KYB process can be completed via API, or a verification link will be sent to the business representative via email.

***

### 2. Authentication

All API requests must be authenticated using an API key. You can obtain your API key from the Yativo Business API dashboard. Include this key in the header of your requests as follows:

```
Authorization: Bearer YOUR_API_KEY
```

***

### 3. Endpoints

#### **Verify Business**

* **Endpoint:** `POST {{baseUrl}}/verification/verify-customer`
* **Description:** Verify the identity of a business.

**Headers:**

```
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

#### **Request Parameters**

| Parameter                                | Type                | Required | Description                                                                     |
| ---------------------------------------- | ------------------- | -------- | ------------------------------------------------------------------------------- |
| type                                     | string              | Yes      | The type of entity (e.g., "business").                                          |
| registered\_address.street\_line\_1      | string              | Yes      | The first line of the business address.                                         |
| registered\_address.city                 | string              | Yes      | The city of the business address.                                               |
| registered\_address.subdivision          | string              | No       | The state/province (ISO 3166-2 code). Required if the country has subdivisions. |
| registered\_address.postal\_code         | string              | Yes      | The postal/ZIP code of the business address.                                    |
| registered\_address.country              | string (ISO 3166-1) | Yes      | The country code (e.g., "USA" for America, "NGA" for Nigeria).                  |
| business\_type                           | string              | Yes      | The business type (e.g., "corporation").                                        |
| business\_industry                       | string              | Yes      | Industry classification code.                                                   |
| compliance\_screening\_explanation       | string              | No       | Explanation for compliance screening.                                           |
| business\_description                    | string              | Yes      | A brief description of the business.                                            |
| email                                    | string              | Yes      | Business email address.                                                         |
| is\_dao                                  | boolean             | Yes      | Indicates if the business is a DAO (Decentralized Autonomous Organization).     |
| is\_high\_risk                           | boolean             | Yes      | Indicates if the business operates in a high-risk industry.                     |
| business\_legal\_name                    | string              | Yes      | The registered legal name of the business.                                      |
| has\_material\_intermediary\_ownership   | boolean             | Yes      | Indicates if there is intermediary ownership.                                   |
| service\_usage\_description              | string              | Yes      | Description of how the service will be used.                                    |
| estimated\_annual\_revenue\_usd          | string              | Yes      | Estimated annual revenue range.                                                 |
| expected\_monthly\_payments\_usd         | number              | Yes      | Expected monthly transaction volume in USD.                                     |
| operates\_in\_prohibited\_countries      | string              | Yes      | Whether the business operates in restricted regions.                            |
| account\_purpose                         | string              | Yes      | Purpose of the business account.                                                |
| account\_purpose\_other                  | string              | No       | Required if account\_purpose includes "other".                                  |
| high\_risk\_activities                   | array of strings    | Yes      | Indicates if the business is engaged in high-risk activities.                   |
| source\_of\_funds                        | string              | Yes      | Source of funds for the business.                                               |
| source\_of\_funds\_description           | string              | No       | Additional details about the source of funds.                                   |
| conducts\_money\_services                | boolean             | Yes      | Whether the business provides money services.                                   |
| conducts\_money\_services\_using\_bridge | boolean             | Yes      | Whether the business uses an intermediary for money services.                   |
| identifying\_information                 | array of objects    | Yes      | Contains the business's identity details.                                       |
| documents                                | array of objects    | No       | Additional documentation provided.                                              |
| ultimate\_beneficial\_owners             | array of objects    | Yes      | Details of individuals who own or control the business.                         |

#### **Example Request**

```json
{
    "type": "business",
    "registered_address": {
        "street_line_1": "123 Main St",
        "city": "New York City",
        "subdivision": "New York",
        "postal_code": "10001",
        "country": "USA"
    },
    "business_type": "corporation",
    "business_industry": "1153",
    "compliance_screening_explanation": "Business compliance screening details",
    "business_description": "A business",
    "email": "team@business.co",
    "is_dao": false,
    "is_high_risk": false,
    "business_legal_name": "My Business",
    "has_material_intermediary_ownership": false,
    "service_usage_description": "Service usage details",
    "estimated_annual_revenue_usd": "250000000_plus",
    "expected_monthly_payments_usd": 101307,
    "operates_in_prohibited_countries": "no",
    "account_purpose": "receive_payments_for_goods_and_services",
    "account_purpose_other": null,
    "high_risk_activities": [
        "none_of_the_above"
    ],
    "source_of_funds": "business_loans",
    "source_of_funds_description": "Minima aperiam cum aut.",
    "conducts_money_services": true,
    "conducts_money_services_using_bridge": true,
    "identifying_information": [
        {
            "type": "ein",
            "issuing_country": "usa",
            "number": "xxx-xx-xxxx"
        }
    ],
    "documents": [
        {
            "purposes": ["statement_of_funds"],
            "file": "data:image/jpg;base64,..."
        }
    ],
    "ultimate_beneficial_owners": [
        {
            "first_name": "John",
            "last_name": "Doe",
            "birth_date": "1990-01-01",
            "email": "john.doe@gmail.com",
            "phone": "1234567890",
            "identifying_information": [
                {
                    "type": "ssn",
                    "issuing_country": "usa",
                    "number": "xxx-xx-xxxx"
                }
            ]
        }
    ]
}
```

***

### 4. Error Codes

| Status Code | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| 200         | Request was successful.                                     |
| 400         | Bad request. The request parameters are invalid or missing. |
| 401         | Unauthorized. The API key is missing or invalid.            |
| 403         | Forbidden. You do not have access to this resource.         |
| 404         | Not found. The requested resource could not be found.       |
| 500         | Internal server error. An error occurred on the server.     |

***
