---
description: >-
  his page outlines the security measures in place and the authentication
  methods required to interact with the Yativo Business API.
---

# Security

At Yativo, we prioritize the security of your business data and transactions.

#### 1. Secure Business Dashboard

The Yativo Business Dashboard provides a secure environment for managing your business operations. Security features include:

* **Magic Sign-In/OTP**: To ensure ease of use and security, users can sign in using a magic link or a One-Time Password (OTP) sent to their registered email or phone number.
* **Two-Factor Authentication (2FA)**: For added security, users have the option to enable Two-Factor Authentication (2FA). With 2FA enabled, access to the dashboard requires an additional verification step, typically through an authentication app or SMS.

#### 2. Access Tokens

To interact with the Yativo Business API, users must obtain an Access Token. The Access Token is used to authenticate API requests and should be included in the `Authorization` header as a Bearer token.

**Example:**

```json
GET /api/v1/businesses HTTP/1.1
Host: api.yativo.com
Authorization: Bearer {access_token}
```

**Important Notes:**

* **Token Expiry**: Access Tokens have a limited lifespan for security reasons. Ensure that tokens are refreshed before they expire to maintain seamless API interactions.
* **Token Security**: Keep your Access Tokens secure. Do not expose them in client-side code or publicly accessible locations.

#### 3. Encryption

Yativo ensures that all sensitive data, including personal information and financial details, is encrypted both at rest and in transit. Our encryption protocols adhere to industry standards to safeguard user data from unauthorized access and breaches.

* **Data Encryption**: All user data stored within Yativo systems is encrypted using AES-256 encryption.
* **Transport Layer Security (TLS)**: All API requests and responses are encrypted via TLS to prevent interception or tampering.

#### 4. Authentication of Requests

All requests made to the Yativo Business API must be authenticated. Unauthorized requests will be rejected with an appropriate HTTP status code (e.g., 401 Unauthorized).

* **Bearer Token**: Include the Access Token as a Bearer token in the `Authorization` header of each API request.

#### 5. KYC and KYB Compliance

To ensure compliance with regulatory standards, Yativo mandates that all businesses complete Know Your Customer (KYC) and Know Your Business (KYB) procedures.

* **Mandatory for Transactions**: KYC and KYB are mandatory for making payment transactions through the Yativo platform. Without successful completion of these processes, payment transactions will be restricted.
* **Verification**: KYC and KYB verification involves the submission and validation of required documentation, including business registration details and personal identification of key stakeholders.

#### 6. Best Practices for API Security

To further enhance the security of your interactions with the Yativo Business API, consider the following best practices:

* **Use 2FA**: Enable Two-Factor Authentication (2FA) on your Yativo Business Dashboard for an extra layer of protection.
* **Limit Token Scope**: Where possible, use tokens with limited scopes to restrict access to only the necessary API endpoints.
* **Monitor API Usage**: Regularly monitor your API usage for any unusual or unauthorized activity.
