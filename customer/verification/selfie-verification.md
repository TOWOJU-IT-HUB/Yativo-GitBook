# Selfie Verification

#### Selfie Verification

* **Endpoint:** `POST {{baseUrl}}/verification/verify-selfie`
* **Description:** Verify a customer's selfie against their photo ID.
* **Headers:**
  * `Authorization: Bearer YOUR_API_KEY`
  * `Content-Type: application/json`

**Request Parameters:**

| Parameter      | Type   | Required | Description                                             |
| -------------- | ------ | -------- | ------------------------------------------------------- |
| `customer_id`  | string | Yes      | The unique ID of the customer.                          |
| `selfieimage`  | string | Yes      | Base64 encoded string of the customer's selfie image.   |
| `photoidimage` | string | Yes      | Base64 encoded string of the customer's photo ID image. |

**Request Example:**

```
{
    "customer_id": "2f103e55-1dc5-40bd-a78c-a4574f7a50e6",
    "selfieimage": "xoxo",
    "photoidimage": "xoxo"
}
```
