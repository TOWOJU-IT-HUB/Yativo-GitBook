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

# Get Transactions

## API Documentation: Get Virtual Card Transactions

### Endpoint

**GET** `{{baseUrl}}/customer/virtual/cards/get/{{card_id}}`

### Description

This endpoint retrieves the transaction history of a specific virtual card using the card's unique identifier.

### Headers

No specific headers are required for this endpoint, but typically, you might need to include authorization tokens or other headers as per your API's authentication requirements.

### Response

The response will include the status of the request, a relevant message, and a list of transactions associated with the specified virtual card if the request is successful. If the request is invalid, an error message will be returned.





{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/customer/virtual/cards/transactions/c9aa5757-c22d-48ca-a08b-aebdee325fde" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

#### Successful Response

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": "c38862c9-f25a-489d-9f1d-0ecf345cd4bd",
            "createdAt": "2024-05-29T19:52:00.911Z",
            "updatedAt": "2024-05-29T19:52:24.538Z",
            "amount": "4",
            "centAmount": "400",
            "type": "debit",
            "method": "withdrawal",
            "narrative": "Withdraw from card",
            "status": "success",
            "currency": "usd",
            "reference": "3bf220468ccc",
            "cardId": "8d5b43bb-683b-45b3-9d1d-f64d5d75ee97"
        },
        {
            "id": "5a4e6ba6-80d6-47b1-9123-e4156bc86cbe",
            "createdAt": "2024-05-29T19:13:26.808Z",
            "updatedAt": "2024-05-29T19:13:26.808Z",
            "amount": "2",
            "centAmount": "200",
            "type": "credit",
            "method": "topup",
            "narrative": "Top-up card",
            "status": "success",
            "currency": "usd",
            "reference": "8d5b43bb-683b-45b3-9d1d-f64d5d75ee97",
            "cardId": "8d5b43bb-683b-45b3-9d1d-f64d5d75ee97"
        },
        {
            "id": "8443227b-0cd0-4a04-a16e-65fc20225f09",
            "createdAt": "2024-05-29T17:27:20.008Z",
            "updatedAt": "2024-05-29T17:27:20.008Z",
            "amount": "5",
            "centAmount": "500",
            "type": "credit",
            "method": "topup",
            "narrative": "Top-up card",
            "status": "success",
            "currency": "usd",
            "reference": "68e64b50-9112-4e41-93b0-20550acd8832",
            "cardId": "8d5b43bb-683b-45b3-9d1d-f64d5d75ee97"
        }
    ]
}
```

#### Error Response

If the request is invalid or there are issues processing the request, the following error response will be returned:

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "error": "Error encountered, please check your request"
    }
}
```

### Fields in Successful Response

* **status**: Indicates the success status of the request (e.g., "success").
* **status\_code**: HTTP status code of the response (e.g., 200 for success).
* **message**: A message describing the result of the request (e.g., "Request successful").
* **data**: Contains a list of transactions related to the virtual card.
  * **id**: Unique identifier of the transaction.
  * **createdAt**: The timestamp when the transaction was created.
  * **updatedAt**: The timestamp when the transaction was last updated.
  * **amount**: The amount involved in the transaction.
  * **centAmount**: The amount in cents (useful for handling currencies that require precision).
  * **type**: Type of the transaction (e.g., "debit" or "credit").
  * **method**: Method of the transaction (e.g., "withdrawal" or "topup").
  * **narrative**: Description or narrative of the transaction.
  * **status**: Status of the transaction (e.g., "success").
  * **currency**: Currency used in the transaction (e.g., "usd").
  * **reference**: Reference identifier for the transaction.
  * **cardId**: Unique identifier of the virtual card associated with the transaction.

By following the above details, you can retrieve the transaction history for a specific virtual card.



{% openapi src="broken-reference" path="/customer/virtual/cards/transactions/{cardId}" method="get" %}
[Broken link](broken-reference)
{% endopenapi %}
