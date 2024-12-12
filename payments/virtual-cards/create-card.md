# Create card

## API Documentation: Create Virtual Card

### Endpoint

**POST** `{{baseUrl}}/customer/virtual/cards/create`

### Description

This endpoint allows you to create a new virtual card for a customer. The customer must already be registered and activated for virtual card services.

### Card Issuing Fees

These fees apply to both MasterCard and Visa Virtual USD cards.

<table><thead><tr><th width="218">Action</th><th>Cost</th></tr></thead><tbody><tr><td><strong>Card Creation</strong></td><td>$2 for every newly issued card</td></tr><tr><td><strong>Top Up</strong></td><td>⁠1.5% charges on virtual card funding</td></tr><tr><td><strong>Chargeback</strong></td><td>$80 flat rate for Visa Card</td></tr><tr><td><strong>Termination</strong></td><td>no fee is charged for the termination of cards, you get back the balance on the card</td></tr><tr><td><strong>Cross Border Fees</strong></td><td>2.5% + $0.5 per transaction settled outside the USA</td></tr><tr><td><strong>Card Declined</strong></td><td>$1 for automatic termination after 3 Insufficient funds Transactions</td></tr></tbody></table>

### Headers

No specific headers are required for this endpoint, but typically, you might need to include authorization tokens or other headers as per your API's authentication requirements.

### Request Body

The request body must include the following fields:

* **customer\_id**: (string) The unique identifier of the customer.
* **amount**: (string) The initial amount to be loaded onto the virtual card.

#### Example Request Body

```json
{
    "customer_id": "4e6e40e8-c148-4eea-9332-76ec98ecb165",
    "amount": "5"
}
```

### Response

The response will include the status of the request, a relevant message, and details of the newly created virtual card if the request is successful. If the request is invalid, an error message will be returned.

#### Successful Response

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Virtual card created successfully",
    "data": {
        "id": "8d5b43bb-683b-45b3-9d1d-f64d5d75ee97",
        "balance": 5,
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

#### Error Response

If the request is invalid or there are issues processing the request, the following error response will be returned:

```json
{
    "error": "Invalid request"
}
```

### Fields in Successful Response

* **status**: Indicates the success status of the request (e.g., "success").
* **status\_code**: HTTP status code of the response (e.g., 200 for success).
* **message**: A message describing the result of the request (e.g., "Virtual card created successfully").
* **data**: Contains the details of the newly created virtual card.
  * **id**: Unique identifier of the virtual card.
  * **balance**: Initial balance loaded onto the virtual card.
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

By following the above details, you can successfully create a new virtual card for a customer.



{% swagger src="../../.gitbook/assets/Zee_v3_OpenAPI.yaml" path="/customer/virtual/cards/create" method="post" %}
[Zee_v3_OpenAPI.yaml](../../.gitbook/assets/Zee_v3_OpenAPI.yaml)
{% endswagger %}
