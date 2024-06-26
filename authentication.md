---
coverY: 0
---

# Authentication

#### Yativo Authentication System

The Yativo API provides an <mark style="background-color:orange;">`auth/login`</mark> endpoint that allows you to generate a bearer token by passing your account credentials. This token is essential for accessing protected resources within the Yativo system.

**Example Request**

To request a bearer token, send a POST request to the `auth/login` endpoint with your `account_id` and `app_secret`.

**Endpoint URL:**

```plaintext
POST {{baseUrl}}/auth/login
```

**Request Headers:**

```plaintext
Content-Type: application/json
```

**Request Body:**

```json
{
  "account_id": "account_id",
  "app_secret": "app_secret"
}
```

**Example Request Using cURL:**

```sh
curl -X POST {{baseUrl}}/auth/login \
-H "Content-Type: application/json" \
-d '{
    "account_id": "account_id",
    "app_secret": "app_secret"
}'
```

**Example Response**

Upon successful authentication, the response will include the `access_token`, `token_type`, and `expires_in` fields.

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOi8vMTI3LjAuMC4xOjkwMDAvYXBpL3YxL2F1dGgvbG9naW4iLCJpYXQiOjE3MTY4OTg0NTQsImV4cCI6MTcxNjg5OTA1NCwibmJmIjoxNLCJqdGkiOiJsZWZEejJGZW1WQjR5YnNBIiwic3ViIjoiNyIsInBydiI6IjIzYmQ1Yzg5NDlmNjAwYWRiMzllNzAxYzQwMDg3MmRiN2E1OTc2ZjcifQ.U7tM5B45f64eCsEk5t0nJFepsKo2tvjyAJEqu8Gh2tk",
        "token_type": "bearer",
        "expires_in": 600
    }
}
```

**Using the Bearer Token**

Once you have the `access_token`, include it in the `Authorization` header for all subsequent API requests to protected endpoints.

**Example Header:**

```plaintext
Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOi8vMTI3LjAuMC4xOjkwMDAvYXBpL3YxL2F1dGgvbG9naW4iLCJpYXQiOjE3MTY4OTg0NTQsImV4cCI6MTcxNjg5OTA1NCwibmJmIjoxNLCJqdGkiOiJsZWZEejJGZW1WQjR5YnNBIiwic3ViIjoiNyIsInBydiI6IjIzYmQ1Yzg5NDlmNjAwYWRiMzllNzAxYzQwMDg3MmRiN2E1OTc2ZjcifQ.U7tM5B45f64eCsEk5t0nJFepsKo2tvjyAJEqu8Gh2tk
```

By following these steps, you can authenticate with the Yativo API and securely access its protected resources using the provided bearer token.
