# Single crypto deposit history

### Endpoint: `/crypto/deposit-history/:id`

#### Description

The `/crypto/deposit-history/:id` endpoint allows businesses to retrieve detailed information about a specific cryptocurrency deposit transaction. This endpoint is useful for viewing the status, amount, and other details of an individual deposit.

#### Request Method

* `GET /crypto/deposit-history/:id`

#### Path Parameter

* **`id`**: The unique identifier of the deposit transaction that you want to retrieve.

#### Response Fields

* **`transactionId`**: The unique identifier of the deposit transaction.
* **`amount`**: The amount of cryptocurrency deposited.
* **`currency`**: The type of cryptocurrency (e.g., BTC, ETH).
* **`status`**: The current status of the deposit (`pending`, `completed`, `failed`).
* **`walletAddress`**: The cryptocurrency wallet address to which the deposit was made.
* **`transactionHash`**: The blockchain transaction hash associated with the deposit.
* **`createdAt`**: The timestamp when the deposit transaction was initiated.
* **`updatedAt`**: The timestamp of the last update to the transaction's status.
* **`confirmations`**: The number of blockchain confirmations the deposit has received.
* **`network`**: The blockchain network on which the transaction was conducted (e.g., Bitcoin, Ethereum).



{% openapi src="../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml" path="/crypto/deposit-history/333a25d6-c273-4b8f-8870-a79deaaaa324" method="get" %}
[Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml](<../../.gitbook/assets/Zee v3.postman_collectionagain.json-OpenApi3Yaml.yaml>)
{% endopenapi %}

{% openapi src="broken-reference" path="/crypto/deposit-history/{cryptoDepositId}" method="get" %}
[Broken link](broken-reference)
{% endopenapi %}
