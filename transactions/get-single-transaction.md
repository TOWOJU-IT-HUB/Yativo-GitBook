# Get Single Transaction

The `/transaction/:id` endpoint allows businesses to retrieve detailed information about a specific transaction using its unique transaction ID. This endpoint is useful for tracking the status, reviewing details, and auditing individual transactions.

### Endpoint: `/transaction/:id`

#### Description

This endpoint retrieves detailed information about a single transaction identified by the `:id` parameter. The response includes all relevant details of the transaction, such as the transaction type, status, amount, timestamps, and any additional metadata.

#### Request Method

* `GET /transaction/:id`

#### URL Parameters

* **`:id`** (required): The unique identifier of the transaction you want to retrieve.
