---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Top up card

### Endpoint

**POST** `{{baseUrl}}/customer/virtual/cards/topup`

### Description

This endpoint allows you to top up a virtual card with a specified amount for a customer.&#x20;

### Card Issuing Fees

These fees apply to both MasterCard and Visa Virtual USD cards.

<table><thead><tr><th width="200">Action</th><th>Cost</th></tr></thead><tbody><tr><td><strong>Card Creation</strong></td><td>$1 for every newly issued card</td></tr><tr><td><strong>Top Up</strong></td><td>$1 if funding is below $100 and 1% if funding is equal to or above $100</td></tr><tr><td><strong>Chargeback</strong></td><td>$60 flat rate for Visa Card</td></tr><tr><td><strong>Termination</strong></td><td>no fee is charged for the termination of cards, you get back the balance on the card</td></tr><tr><td><strong>Cross Border Fees</strong></td><td>2.5% + $0.5 per transaction settled outside the USA</td></tr><tr><td><strong>Card Declined</strong></td><td>$1 for automatic termination after 3 Insufficient funds Transactions</td></tr></tbody></table>

### Headers

No specific headers are required for this endpoint, but typically, you might need to include authorization tokens or other headers as per your API's authentication requirements.

### Request Body

The request body must include the following fields:

* **customer\_id**: (string) The unique identifier of the customer.
* **cardId**: (string) The unique identifier of the virtual card.
* **amount**: (number) The amount to top up the virtual card.

#### Example Request Body

```json
{
    "customer_id": "{{customer_id}}",
    "cardId": "{{card_id}}",
    "amount": 2
}
```

### Response

The response will include the status of the request, a relevant message, and details about the top-up operation.

#### Insufficient Balance Error Response

If the customer's wallet is empty and the top-up cannot be completed, the following error response will be returned:

```json
{
    "status": "failed",
    "status_code": 400,
    "message": "Request failed",
    "data": {
        "error": "Wallet is empty"
    }
}
```

Or if there is an error confirming the card's activation status, the following error response will be returned:

```json
{
    "status": "failed",
    "status_code": 400,
    "message": "Request failed",
    "data": {
        "error": "Error please confirm card is active, or contact support if error persist"
    }
}
```

#### Successful Response

If the top-up request is successful and in progress, the following success response will be returned:

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "message": "card topup in progress"
    }
}
```

### Fields in Error Response

* **status**: Indicates the failure status of the request (e.g., "failed").
* **status\_code**: HTTP status code of the response (e.g., 400 for client errors).
* **message**: A message describing the result of the request (e.g., "Request failed").
* **data**: Contains details about the error encountered.
  * **error**: A message indicating the specific error (e.g., "Wallet is empty" or "Error please confirm card is active, or contact support if error persist").

### Fields in Successful Response

* **status**: Indicates the success status of the request (e.g., "success").
* **status\_code**: HTTP status code of the response (e.g., 200 for success).
* **message**: A message describing the result of the request (e.g., "Request successful").
* **data**: Contains details about the top-up operation.
  * **message**: A message indicating that the card top-up is in progress.

By following the above details, you can successfully top up a virtual card for a customer.
