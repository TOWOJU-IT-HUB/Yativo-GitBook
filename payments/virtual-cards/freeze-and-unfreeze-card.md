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

# Freeze and Unfreeze Card

### Endpoint

**POST** `{{baseUrl}}/customer/virtual/cards/update/{{card_id}}`

### Description

This endpoint allows you to freeze or unfreeze a virtual card using the card's unique identifier. Freezing a card prevents any transactions from being processed until it is unfrozen.

### Headers

No specific headers are required for this endpoint, but typically, you might need to include authorization tokens or other headers as per your API's authentication requirements.

### Request Body

The request body must include the action you want to perform on the virtual card. It can either be "freeze" or "unfreeze".

#### Example Request Body

```json
{
    "action": "freeze"
}
```

or

```json
{
    "action": "unfreeze"
}
```

###

{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/customer/virtual/cards/update/c9aa5757-c22d-48ca-a08b-aebdee325fde" method="put" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

### Response

The response will include the status of the request, a relevant message, and details about the action performed if the request is successful. If there is an error, a message indicating the issue will be returned.

#### Successful Unfreeze Response

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "action": "unfreeze card successful"
    }
}
```

#### Successful Freeze Response

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "action": "freeze card successfully"
    }
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
* **data**: Contains details about the action performed on the virtual card.
  * **action**: A message indicating the action that was successfully performed (e.g., "unfreeze card successful" or "freeze card successfully").

### Fields in Error Response

* **status**: Indicates the success status of the request (in this case, still "success" but with an error in the data).
* **status\_code**: HTTP status code of the response (e.g., 200 for processed requests).
* **message**: A message describing the result of the request (e.g., "Request successful").
* **data**: Contains details about the error encountered.
  * **error**: A message indicating the issue (e.g., "Error encountered, please check your request").

By following the above details, you can successfully freeze or unfreeze a virtual card.



{% openapi src="broken-reference" path="/customer/virtual/cards/update/{cardId}" method="put" %}
[Broken link](broken-reference)
{% endopenapi %}
