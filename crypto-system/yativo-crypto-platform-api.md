# Yativo Crypto Platform API

**Welcome to the Yativo Crypto Platform API!**

This API is part of the **Yativo Fintech-as-a-Service (FaaS) infrastructure**, designed to empower businesses with the tools to integrate cryptocurrency capabilities into their platforms seamlessly. The Crypto Platform enables features like wallet management, customer account handling, transaction processing, asset pricing, and webhook notifications.

### **Base URL**

The API's base URL for all requests is:

```arduino
https://crypto-api.yativo.com
```

Ensure that all endpoints are appended to this base URL. For example, to retrieve all accounts, use:

```bash
GET https://crypto-api.yativo.com/api/v1/accounts
```

***

### **Key Features**

* **Account Management**: Create and manage primary accounts and sub-accounts for users.
* **Wallet Integration**: Link wallets to accounts for secure storage and operations.
* **Gas Station**: Enable businesses to cover gas fees for blockchain transactions on networks like BEP20, independently of Yativo fees.
* **Customer Management**: Add, update, and retrieve customer profiles for seamless integration with your platform.
* **Real-Time Market Prices**: Fetch the latest market prices for supported crypto assets.
* **Transaction Handling**: Monitor and retrieve transaction histories with detailed statuses.
* **Webhooks**: Automate notifications for key events like completed transactions or account changes.

***

### **Getting Started**

To get started, follow these steps:

#### 1. **Authentication**

All requests must include a bearer token for authentication. Obtain this token by logging in with your credentials.

* Endpoint: `POST /api/authentication/login`

Include the token in the `Authorization` header for subsequent API requests:

```makefile
Authorization: Bearer <your-token>
```

#### 2. **KYC Requirements**

* **For Business Users**: Complete Yativo’s KYC verification to activate your account.
* **For End Users**: Ensure all customer accounts undergo KYC compliance before activating wallets or performing transactions.

#### 3. **Set Up Your Gas Station**

The Gas Station wallet allows you to cover gas fees for blockchain transactions on behalf of your users.

* Create your Gas Station: `POST /api/v1/accounts/gas-station/create`
* Deposit assets like BNB for BEP20 transactions.

#### 4. **Start Building**

* Create customer accounts: `POST /api/v1/customers`
* Create primary and sub-accounts for users: `POST /api/v1/accounts/sub-accounts`
* Fetch live crypto asset prices: `GET /api/v1/assets/prices`

***

### **Example Request**

#### Get Account Balance

Fetch the balance of a specific account.

**Request**:

```bash
GET https://crypto-api.yativo.com/api/v1/accounts/{account_id}/balance  
Authorization: Bearer <your-token>
```

**Response**:

```json
{
    "account_id": "acc123",
    "balance": "1500.00",
    "currency": "BNB"
}
```

***

### **Documentation**

For a detailed explanation of all endpoints, refer to the complete [Yativo Crypto Platform API Documentation](broken-reference).

***

### **Support**

For questions or assistance, contact us at support@yativo.com.

**Yativo** — Empowering your fintech journey with scalable, secure, and efficient solutions.
