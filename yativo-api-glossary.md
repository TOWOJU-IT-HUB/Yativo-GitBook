---
description: >-
  Welcome to the Yativo API Glossary. Here you'll find definitions of key terms
  used throughout the documentation to help you better understand our platform
  and services.
---

# Yativo API Glossary

### Glossary of Terms

#### **Business**

A registered entity using Yativo’s Banking-as-a-Service platform. A business account must be verified to access Yativo’s API services and dashboard.

#### **baseUrl**

The base URL is the root address for accessing the Yativo API endpoints. It is the primary domain followed by specific paths for different API functionalities.

* Example: `https://api.yativo.com`

#### **Payin**

A transaction type where funds are deposited into a business account. This can involve customer payments, deposits, or any inflow of money into the business account.

#### **Payout**

A transaction type where funds are withdrawn or transferred out of a business account. This can involve paying vendors, transferring funds to another account, or any outflow of money from the business account.

#### **Customers**

The end-users or clients of the business utilizing Yativo’s services. These are the individuals or entities that interact with the business's financial products and services.

#### **API Key**

A unique identifier used to authenticate requests associated with your Yativo account. It ensures secure communication between your application and the Yativo API.

#### **Bearer Token**

A type of token used for authenticating API requests. It must be included in the Authorization header of requests to access protected resources.

* Example: `Authorization: Bearer your_access_token`

#### **Dashboard**

The online interface provided by Yativo for managing your business account, settings, API keys, and monitoring transaction activities.

#### **Endpoint**

A specific URL path that allows interaction with the Yativo API for performing various operations, such as `auth/login`, `payin`, and `payout`.

#### **Account ID**

A unique identifier for your business account within the Yativo system. It is used in API requests to specify and authenticate your account.

#### **App Secret**

A confidential key associated with your API keys that helps authenticate and authorize your API requests. It should be kept secure and not shared publicly.

**FBO (For Benefit Of) Virtual Accounts:**

These accounts are utilized by Yativo Businesses to manage and store funds separately, often for specific purposes such as transactions, payments, or escrow services.

**End-user Virtual Accounts**

End-user Virtual Accounts are sub-wallets provided to Yativo Business Customers under their name within the Yativo platform, These accounts enable Yativo Business Customers to manage funds distinctively for their own transactions, payments, or other financial activities facilitated through the Yativo API.

**Beneficiary**

* **Definition:** A beneficiary within the Yativo API context is an individual or entity designated to receive payments or transfers initiated by a Yativo Business Customer.
* **Explanation:** This designation ensures that funds or payments processed through Yativo are directed to the intended recipient, whether an individual or an organization.

**End-user Beneficiary**

End-user Virtual Accounts are beneficiaries of end-user accounts.

**Payment Details**

Payment Details encompass specific information related to a financial transaction or payment process within the Yativo API. These details typically include data such as account numbers, routing information, beneficiary details, and any other pertinent information required to complete a payment or transfer, these details vary by the payment method and gateway.

**Dynamic Form**

A Dynamic Form within the Yativo API is a form that has it's form fields populated by the response body of an endpoint.

**Exchange Rate**

Exchange Rate refers to the rate at which one currency can be exchanged for another currency, exchange rates are used to calculate the equivalent value of one currency in terms of another, facilitating currency conversions for transactions or financial operations.









***

By familiarizing yourself with these terms, you’ll have a better understanding of how to effectively use the Yativo API and its features. For more detailed explanations and examples, refer to the relevant sections in the Yativo API Documentation. If you have any questions or need further assistance, please contact our [Support Center](https://www.yativo.com/support).
