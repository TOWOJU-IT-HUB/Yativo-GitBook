---
hidden: true
---

# Accounts

#### Overview

Accounts are central to how Yativo operates. An **account** represents a primary crypto wallet for a user or business. **Sub-accounts** allow for finer-grained wallet management and delegation.

#### Use Case

* **For Businesses:** Use accounts to manage company wallets and allocate sub-accounts to individual customers.
* **For End Users:** Provide wallet functionality for storing, sending, and receiving crypto.

#### Endpoints

**Get All Accounts**

* **URL:** `GET /api/v1/accounts`
* **Description:** Fetches all accounts associated with the authenticated user.
* **Implementation Context:**
  * Use to display an account dashboard with wallet balances for an admin or a customer.
* **Response Example:**
* ```json
  [
      {
          "account_id": "acc123",
          "name": "Business Wallet",
          "balance": "5000.00",
          "currency": "USDT"
      }
  ]
  ```

**Create Sub-Account**

* **URL:** `POST /api/v1/accounts/sub-accounts`
* **Description:** Creates a sub-account under a parent account.
* **Implementation Context:**
  * Ideal for creating wallets for individual customers under a business umbrella.
  * Sub-accounts can be used to segregate funds for specific users or purposes.
* **Request Example:**
* ```json
  {
      "name": "Customer Wallet",
      "account_id": "acc123",
      "customer_id": "cus456"
  }
  ```
* **Response Example:**

```json
{
    "status": "success",
    "sub_account_id": "sub123",
    "message": "Sub-account created successfully."
}
```
