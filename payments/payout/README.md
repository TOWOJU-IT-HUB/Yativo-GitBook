# Payout

The Yativo Business API provides a comprehensive suite of endpoints to manage payouts, enabling businesses to efficiently handle financial transactions. This documentation outlines the processes for initiating single payouts, executing batch payouts, and retrieving payout details.

### Single Payout

The Single Payout endpoint allows businesses to send funds to a recipient's bank account or wallet. This is typically used for one-off payments where a specified amount is transferred to a specific recipient. The process requires details such as the recipient's ID, the amount to be transferred, and the payment method. The response will include a unique identifier for the payout, along with the status of the transaction.

### Batch Payout

The Batch Payout endpoint facilitates the transfer of funds to multiple recipients in a single request. This is particularly useful for mass payments, such as payroll or disbursements to a large number of clients. Each payout within the batch requires details similar to a single payout, including the recipient's ID, the amount, and the payment method. The response provides a unique batch identifier and the status of each payout in the batch.

### Get Payout

The Get Payout endpoint allows businesses to retrieve detailed information about a specific payout using its unique payout ID. This endpoint is essential for tracking the status of a payout, confirming its completion, or investigating any issues related to the transaction. The response will provide comprehensive details about the payout, including the amount, recipient information, status, and timestamps.

### Get Payouts

The Get Payouts endpoint enables businesses to retrieve a list of all payouts associated with their account. This can include filtering payouts by their status (e.g., pending, completed, failed) and paginating results for easier management of large datasets. This endpoint is valuable for auditing, reconciliation, and monitoring the flow of funds within the business. The response will include details of each payout, such as the payout ID, amount, status, and creation date, along with pagination information to manage the list of results effectively.
