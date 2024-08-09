# Refund Virtual Account Payin

The `/business/virtual-account/refundPayin/:id` endpoint allows businesses to reverse or refund a virtual account transaction that has been previously made. This can be useful in situations where a payment was made in error, or a refund is required.

#### Endpoint

**URL:** `https://api.yativo.com/business/virtual-account/refundPayin/:id`

**Method:** `POST`

#### Path Parameters

| Parameter | Type     | Description                                             |
| --------- | -------- | ------------------------------------------------------- |
| `:id`     | `string` | The unique identifier of the transaction to be refunded |

#### Request Headers

| Header          | Type     | Required | Description                                      |
| --------------- | -------- | -------- | ------------------------------------------------ |
| `Authorization` | `string` | Yes      | Bearer token for authenticating the API request. |
| `Content-Type`  | `string` | Yes      | `application/json`                               |
