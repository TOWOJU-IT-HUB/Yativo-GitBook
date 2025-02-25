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

# Get Payouts

#### Get Payouts API Documentation

**Endpoint: `GET /wallet/payouts?page=1`**

This endpoint retrieves a list of payout records for the authenticated user.

**Request**

* **URL**: `/wallet/payouts`
* **Method**: `GET`
* **Headers**:
  * `Authorization`: Bearer {token}



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/wallet/payouts" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

**Success Response**

* **Status**: 200 OK
*   **Body**:

    ```json
    {
        "status": "success",
        "status_code": 200,
        "message": "Records retrieved successfully",
        "data": [
            {
                "user_id": 1,
                "amount": "3",
                "currency": "PEN",
                "beneficiary_id": "1",
                "status": "pending",
                "raw_data": {
                    "message": "Payout request submitted successfully. Current status: IN PROGRESS"
                },
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
            },
            {
                "user_id": 1,
                "amount": "500",
                "currency": "PEN",
                "beneficiary_id": "1",
                "status": "pending",
                "raw_data": {
                    "message": "Payout request submitted successfully. Current status: IN PROGRESS"
                },
                "created_at": "2024-05-30T16:47:38.000000Z",
                "updated_at": "2024-05-30T18:02:29.000000Z",
                "payout_id": "8e870fa5-2a8f-4379-86b8-0f3fcf3e2b93",
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
            },
            {
                "user_id": 1,
                "amount": "500",
                "currency": "PEN",
                "beneficiary_id": "1",
                "status": "pending",
                "raw_data": {
                    "message": "Payout request submitted successfully. Current status: IN PROGRESS"
                },
                "created_at": "2024-05-30T16:47:08.000000Z",
                "updated_at": "2024-05-30T18:02:31.000000Z",
                "payout_id": "96570c28-aee6-42e7-80c5-2a6ec0be1e7f",
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
            },
            {
                "user_id": 1,
                "amount": "20",
                "currency": "GBP",
                "beneficiary_id": "1",
                "status": "pending",
                "raw_data": {
                    "amount": 20,
                    "beneficiary_id": 1,
                    "payment_method_id": 2
                },
                "created_at": "2024-05-24T13:58:04.000000Z",
                "updated_at": "2024-05-30T18:02:32.000000Z",
                "payout_id": "09eb118d-abeb-4703-9d11-21f96abf4324",
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
        ],
        "pagination": {
            "total": 4,
            "per_page": 10,
            "current_page": 1,
            "last_page": 1,
            "next_page_url": null,
            "prev_page_url": null
        }
    }
    ```

**Explanation:**

1. **`status`**: Indicates the success or failure of the API request.
2. **`status_code`**: The HTTP status code of the response.
3. **`message`**: A message indicating the result of the request.
4. **`data`**: An array of payout records containing the following fields:
   * `user_id`: The ID of the user who initiated the payout.
   * `amount`: The amount of the payout.
   * `currency`: The currency of the payout.
   * `beneficiary_id`: The ID of the beneficiary.
   * `status`: The current status of the payout.
   * `raw_data`: Additional information about the payout.
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
5. **`pagination`**: An object containing pagination details:
   * `total`: The total number of records.
   * `per_page`: The number of records per page.
   * `current_page`: The current page number.
   * `last_page`: The last page number.
   * `next_page_url`: The URL for the next page of records (if applicable).
   * `prev_page_url`: The URL for the previous page of records (if applicable).
