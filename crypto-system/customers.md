---
hidden: true
---

# Customers

#### Overview

Customers are the end users of your platform. Managing their data allows you to map wallet addresses and transactions to individual users.

#### Use Case

* **User Onboarding:** Register customers when they sign up on your platform.
* **Account Linking:** Link customers to sub-accounts for wallet operations.

#### Endpoints

**Create Customer**

* **URL:** `POST /api/v1/customers`
* **Description:** Adds a new customer to your platform.
* **Implementation Context:**
  * Use during onboarding to automatically create a user profile in Yativo.
* **Request Example:**
* ```json
  {
      "name": "Jane Doe",
      "email": "janedoe@example.com",
      "phone": "+123456789"
  }
  ```
* **Response Example:**
* ```json
  {
      "status": "success",
      "customer_id": "cus789",
      "message": "Customer created successfully."
  }
  ```

**Fetch All Customers**

* **URL:** `GET /api/v1/customers`
* **Description:** Retrieve all customers associated with your account.
* **Response Example:**
* ```json
  [
      {
          "customer_id": "cus123",
          "name": "John Doe",
          "email": "johndoe@example.com"
      }
  ]
  ```
