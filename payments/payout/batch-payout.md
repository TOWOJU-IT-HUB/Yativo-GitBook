---
hidden: true
---

# Batch Payout

#### Batch Payouts API Documentation

**Endpoint: `POST`**` `` ``{{baseUrl}}/payout/batch `

This endpoint processes batch payout requests. It validates the input data, checks if beneficiaries and their payment methods exist, creates withdrawal records, and processes payouts using a payment service.

**Request**

* **URL**: `{{baseUrl}}/payout/batch`
* **Method**: `POST`
* **Content-Type**: `application/json`
*   **Request Body**:

    ```json
    {
        "payouts": [
            {
                "beneficiary_id": 1,
                "amount": 100.00,
                "beneficiary_details_id": 1
            },
            {
                "beneficiary_id": 2,
                "amount": 150.00,
                "beneficiary_details_id": 2
            }
        ]
    }
    ```

**Response**

* **Success Response**:
  * **Status**: 200 OK
  *   **Body**:

      ```json
      {
          "status": "success",
          "status_code": 200,
          "message": "Batch withdrawal requests processed successfully",
          "data": [
              {
                  "beneficiary_id": 1,
                  "amount": 100.00,
                  "gateway": "example_gateway",
                  "currency": "USD",
                  "transaction_details": { /* payout details */ }
              },
              {
                  "beneficiary_id": 2,
                  "amount": 150.00,
                  "gateway": "example_gateway",
                  "currency": "USD",
                  "transaction_details": { /* payout details */ }
              }
          ]
      }
      ```
* **Error Response**:
  * **Status**: 400 Bad Request
  *   **Body**:

      ```json
      {
          "status": "failed",
          "status_code": 400,
          "message": "Request failed",
          "data": {
              "errors": [
                  {
                      "error": "Beneficiary not found"
                  },
                  {
                      "error": "Beneficiary not found"
                  }
              ]
          }
      }
      ```

**Error Handling**

The following are common error scenarios and their responses:

1. **Validation Errors**:
   * **Status**: 400 Bad Request
   * **Body**: Validation errors will be detailed in the response.
2. **Beneficiary Not Found**:
   * **Status**: 400 Bad Request
   *   **Body**:

       ```json
       {
           "status": "failed",
           "status_code": 400,
           "message": "Request failed",
           "data": {
               "errors": [
                   {
                       "error": "Beneficiary not found"
                   }
               ]
           }
       }
       ```
3. **Invalid Payout Method**:
   * **Status**: 400 Bad Request
   *   **Body**:

       ```json
       {
           "status": "failed",
           "status_code": 400,
           "message": "Request failed",
           "data": {
               "errors": [
                   {
                       "error": "The selected beneficiary has no valid payout method"
                   }
               ]
           }
       }
       ```
4. **Payment Processing Error**:
   * **Status**: 400 Bad Request
   *   **Body**:

       ```json
       {
           "status": "failed",
           "status_code": 400,
           "message": "Request failed",
           "data": {
               "errors": [
                   {
                       "error": "Payment processing error"
                   }
               ]
           }
       }
       ```
5. **Internal Server Error**:
   * **Status**: 500 Internal Server Error
   *   **Body**:

       ```json
       {
           "status": "error",
           "status_code": 500,
           "message": "Internal server error",
           "data": {
               "error": "Detailed error message"
           }
       }
       ```

**Explanation:**

1. **Input Validation**:
   * The request is validated to ensure it contains an array of payouts, each with a `beneficiary_id`, `amount`, and `beneficiary_details_id`.
2. **Error Handling**:
   * If validation fails, an error response is returned immediately.
   * Errors are collected for each payout request and processed at the end.
3. **Database Transaction**:
   * The code runs within a database transaction to ensure atomicity.
   * For each payout, it checks the existence of the beneficiary and the validity of the payment method.
4. **Withdrawal Creation**:
   * If all checks pass, a withdrawal record is created.
   * Payment is processed using the `PayoutService`.
   * Any errors encountered are recorded and returned after processing all payouts.
5. **Response**:
   * A success response includes details of each successful payout.
   * Errors are returned with appropriate status codes and messages.
