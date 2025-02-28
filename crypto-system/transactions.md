---
hidden: true
---

# Transactions

#### Overview

The Transactions API helps track and manage all wallet transactions, ensuring transparency and accountability.

#### Use Case

* **For Businesses:** Reconcile payments by matching transaction IDs.
* **For Users:** Display transaction history on their dashboard.

#### Endpoints

**Get All Transactions**

* **URL:** `GET /api/v1/transactions`
* **Description:** Retrieves all transactions associated with your account.
* **Response Example:**
* ```json
  [
      {
          "transaction_id": "txn123",
          "amount": "50.00",
          "currency": "USDT",
          "status": "completed",
          "timestamp": "2024-11-01T12:34:56Z"
      }
  ]
  ```

**Get Transaction by ID**

* **URL:** `GET /api/v1/transactions/{transaction_id}`
* **Description:** Fetches details of a specific transaction.
* **Response Example:**
* ```json
  {
      "transaction_id": "txn123",
      "amount": "50.00",
      "currency": "USDT",
      "status": "completed",
      "timestamp": "2024-11-01T12:34:56Z"
  }
  ```
