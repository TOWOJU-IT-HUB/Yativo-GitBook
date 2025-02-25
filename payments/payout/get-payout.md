---
layout:
  title:
    visible: false
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Get Payout

#### Fetch Payout Details API Documentation

**Endpoint: `GET /payout/{payout_id}`**

This endpoint retrieves detailed information about a specific payout using its unique identifier (`payout_id`).

**Request**

* **URL**: `/payout/{payout_id}`
* **Method**: `GET`
* **Headers**:
  * `Authorization`: Bearer `{token}`

**URL Parameters**

* **`payout_id`**: The unique identifier of the payout to be fetched.



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/wallet/payout/{payout_id}" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

**Success Response**

* **Status**: 200 OK
*   **Body**:

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Request successful",
        "data": {
            "user_id": 1,
            "amount": "3",
            "currency": "PEN",
            "beneficiary_id": "1",
            "status": "pending",
            "created_at": "2024-05-30T17:12:47.000000Z",
            "updated_at": "2024-05-30T18:02:28.000000Z",
            "payout_id": "79be1bfc-a3fa-4d8d-909d-c9c24d53875d",
            "beneficiary": {
                "id": 1,
                "user_id": 1,
                "recipient_type": "individual",
                "customer_name": "John Smith",
                "customer_email": "john@yativo.com",
                "customer_nickname": "John Smith",
                "country": "Nigeria",
                "customer_address": {
                    "city": "Ikeja",
                    "county": "Lagos",
                    "postal_code": 900901,
                    "address_line_1": "1st episode john doe street",
                    "address_line_2": "this can be null"
                },
                "created_at": "2024-05-08T13:47:11.000000Z",
                "updated_at": "2024-05-08T13:47:11.000000Z"
            }
        }
    }
    ```

**Explanation**

1. **`status`**: Indicates the success of the API request.
2. **`status_code`**: The HTTP status code of the response.
3. **`message`**: A message indicating the result of the request.
4. **`data`**: An object containing details about the specific payout, including:
   * `user_id`: The ID of the user who initiated the payout.
   * `amount`: The amount of the payout.
   * `currency`: The currency of the payout.
   * `beneficiary_id`: The ID of the beneficiary.
   * `status`: The current status of the payout.
   * `created_at`: The timestamp when the payout was created.
   * `updated_at`: The timestamp when the payout was last updated.
   * `payout_id`: The unique identifier for the payout.
   * `beneficiary`: An object containing details about the beneficiary, including:
     * `id`: The ID of the beneficiary.
     * `user_id`: The ID of the user associated with the beneficiary.
     * `recipient_type`: The type of recipient (e.g., individual).
     * `customer_name`: The name of the beneficiary.
     * `customer_email`: The email of the beneficiary.
     * `customer_nickname`: The nickname of the beneficiary.
     * `country`: The country of the beneficiary.
     * `customer_address`: An object containing the address of the beneficiary, including:
       * `city`: The city of the beneficiary.
       * `county`: The county of the beneficiary.
       * `postal_code`: The postal code of the beneficiary.
       * `address_line_1`: The first line of the address.
       * `address_line_2`: The second line of the address (can be null).
     * `created_at`: The timestamp when the beneficiary was created.
     * `updated_at`: The timestamp when the beneficiary was last updated.
