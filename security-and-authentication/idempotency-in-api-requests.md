# Idempotency in API Requests

#### Overview

To ensure **safe retries** and prevent **duplicate operations**, our API requires an `Idempotency-Key` in the **header section** of all `POST`, `PUT`, and `PATCH` requests. This key ensures that the same request is **not processed multiple times unintentionally** due to network issues, client retries, or unexpected failures.

#### Why Idempotency Matters

* **Prevents duplicate transactions:** Ensures that operations like payments or account creation are executed **only once**.
* **Ensures consistency:** The same request with the same key always returns **the same result**.
* **Improves API reliability:** Clients can safely retry requests **without unintended side effects**.

#### How It Works

1. **Client generates a unique key** (e.g., a UUID).
2. The key is sent in the **`Idempotency-Key`** header with the request.
3. **The server checks the key**:
   * If it's a **new key**, the request is **processed**, and the result is **stored**.
   * If the **same key is sent again**, the **stored response** is returned instead of processing the request again.
4. The key **remains valid for a period** (e.g., 24 hours) to allow safe retries.

#### Request Example

**First Attempt:**

```http
POST /api/some-endpoint
Content-Type: application/json
Idempotency-Key: 123e4567-e89b-12d3-a456-426614174000

{
    "amount": 100,
    "currency": "USD",
    "recipient": "john@example.com"
}
```

* The server **processes the request**, records the result, and responds with `200 OK`.

**Retry with the Same Key:**

```http
POST /api/some-endpoint
Content-Type: application/json
Idempotency-Key: 123e4567-e89b-12d3-a456-426614174000

{
    "amount": 100,
    "currency": "USD",
    "recipient": "john@example.com"
}
```

* The server **detects the same key**, does **not** reprocess the request, and **returns the stored response**.

#### Server Behavior

| Scenario                          | Server Action                                       |
| --------------------------------- | --------------------------------------------------- |
| First request with a new key      | Process the request and store the response.         |
| Retried request with the same key | Return the stored response, **no reprocessing**.    |
| Request with a different key      | Treat as a **new request** and process accordingly. |

#### Best Practices

* **Use a UUID** (e.g., `123e4567-e89b-12d3-a456-426614174000`) for `Idempotency-Key` values.
* **Store the key and response** for at least **24 hours** to allow retries.
* **If a request times out, retry it with the same key** to prevent duplicates.
* **If the key is different, the request will be treated as a new operation.**

#### Error Handling

If an `Idempotency-Key` is missing in a `POST`, `PUT`, or `PATCH` request, the API will respond with:

```json
{
    "error": "Idempotency-Key is required for this request."
}
```

If a key is reused after its validity period has expired, the API will return:

```json
{
    "error": "Idempotency-Key expired. Please use a new key."
}
```

#### Yativo API Integration Guide

**1. Sign Up for a Yativo Business Account**

* Visit [Yativo.com](https://yativo.com) and click on the **"Sign Up"** button.
* Fill in the required information to create your account.

**2. Verify Your Business Information**

As part of the sign-up process:

* Provide the necessary documents and details about your business.
* Submit the information for review. Verification typically takes a few business days.

**3. Access the Yativo Dashboard**

Once your business information is verified:

* Log in to your Yativo account.
* Access your dashboard to manage your account settings, monitor your activities, and configure your API usage.

**4. Get Your API Keys**

To start using the Yativo API:

* In your dashboard, go to the **"API Keys"** section.
* Generate your API keys (both public and secret keys) for authentication.
* Keep your API keys secure and do not share them publicly.

**5. Start Using the Yativo API**

With your API keys in hand, you're ready to integrate Yativo's API into your applications:

* Refer to the **Yativo API Documentation** for detailed information on available endpoints, request formats, and usage examples.
* **Use the provided API keys and the `Idempotency-Key` header** to authenticate your requests and interact with the Yativo platform safely.
