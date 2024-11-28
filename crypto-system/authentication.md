# Authentication

#### Overview

Authentication is the starting point for any integration with the Yativo Crypto Platform. All API requests must include a bearer token obtained through the authentication process.

#### Use Case

* **Login Flow:** Your system authenticates itself with Yativo by providing valid credentials, receives a bearer token, and uses this token to access other endpoints.
* **Two-Factor Authentication (2FA):** Add an additional layer of security with Google Authenticator verification.

#### Endpoints

**Login**

* **URL:** `POST /api/authentication/login`
* **Description:** Use this endpoint to log in and obtain an access token.
* **Implementation Context:**
  * Useful for creating an admin panel or backend system for managing wallets and transactions.
  * Should be called before performing any other API operations.
* **Request Example:**
* ```json
  {
      "email": "user@example.com",
      "password": "secure-password"
  }
  ```
* **Response Example:**
* ```json
  {
      "status": "success",
      "token": "eyJhbGciOiJIUzI1NiIs..."
  }
  ```

**Verify Google Authenticator**

* **URL:** `POST /api/authentication/google_auth_verification`
* **Description:** Confirms the user's identity through an OTP provided by Google Authenticator.
* **Implementation Context:**
  * Protect sensitive endpoints like withdrawals or account changes.
  * Ideal for users managing multiple high-value wallets.
* **Request Example:**
* ```json
  {
      "email": "user@example.com",
      "otp": "123456"
  }
  ```
* **Response Example:**
* ```json
  {
      "status": "verified",
      "message": "Authentication successful"
  }
  ```
