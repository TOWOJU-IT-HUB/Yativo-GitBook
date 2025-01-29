# Fetch card

<mark style="color:green;">`POST`</mark> `{{baseUrl}}/customer/virtual/cards/get/{{card_id}}`

### Description

This endpoint retrieves the details of a specific virtual card using the card's unique identifier.

### Headers

No specific headers are required for this endpoint, but typically, you might need to include authorization tokens or other headers as per your API's authentication requirements.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

### Response

The response will include the status of the request, relevant message, and details of the virtual card if the request is successful. If the request is invalid, an error message will be returned.

### Fields in Response

* **status**: Indicates the success status of the request (e.g., "success").
* **status\_code**: HTTP status code of the response (e.g., 200 for success).
* **message**: A message describing the result of the request (e.g., "Request successful").
* **data**: Contains the details of the virtual card if the request is successful.
  * **id**: Unique identifier of the virtual card.
  * **balance**: Current balance of the virtual card.
  * **cardNumber**: Full number of the virtual card.
  * **last4**: Last four digits of the card number.
  * **cardName**: Name on the virtual card.
  * **cardType**: Type of the card (e.g., "virtual").
  * **cardBrand**: Brand of the card (e.g., "visa").
  * **cvv2**: CVV2 code of the virtual card.
  * **expiry**: Expiry date and time of the card in ISO 8601 format.
  * **valid**: Validity of the card in MM/YYYY format.
  * **billingAddress**: Billing address associated with the virtual card.
    * **city**: City of the billing address.
    * **state**: State of the billing address.
    * **street**: Street address.
    * **country**: Country of the billing address.
    * **zipCode**: Postal code of the billing address.
    * **countryCode**: Country code of the billing address.

{% tabs %}
{% tab title="200" %}
```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "id": "8d5b43bb-683b-45b3-9d1d-f64d5d75ee97",
        "balance": 300,
        "cardNumber": "4040381842044628",
        "last4": "4628",
        "cardName": "John Doe",
        "cardType": "virtual",
        "cardBrand": "visa",
        "cvv2": "849",
        "expiry": "2027-05-29T00:00:00",
        "valid": "05/2027",
        "billingAddress": {
            "city": "Miami",
            "state": "Florida",
            "street": "3401 N. Miami, Ave. Ste 230",
            "country": "United States",
            "zipCode": "33127",
            "countryCode": "US"
        }
    }
}
```
{% endtab %}

{% tab title="400" %}
```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": {
        "error": "Invalid request"
    }
}
```
{% endtab %}
{% endtabs %}



{% swagger src="broken-reference" path="/customer/virtual/cards/get/{cardId}" method="get" %}
[Broken link](broken-reference)
{% endswagger %}
