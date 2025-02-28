---
hidden: true
---

# Gas Station

#### Overview

The **Gas Station** is a special wallet feature provided by Yativo that allows business users to store assets like BNB (Binance Coin) to facilitate their users’ transactions on the **BEP20 blockchain**. This setup ensures smooth transaction processing by covering the blockchain's gas fees required for operations such as transfers or token interactions.

#### Key Features

1. **Facilitation of Transactions**:
   * The Gas Station covers blockchain gas fees on behalf of the business’s end users.
   * It operates independently of Yativo, meaning the assets stored in the Gas Station are fully managed and funded by the Yativo business user.
2. **Separation from Yativo Fees**:
   * **Yativo’s Fees**: These are fees charged by Yativo for using its platform or services.
   * **Gas Station**: This wallet is exclusively for covering gas fees for blockchain transactions and does not interact with Yativo’s fee structure.
3. **Custom Fees for End Users**:
   * Yativo business users can configure their own service fees to charge end users, allowing them to maintain profitability or cover operational costs while using the Gas Station to facilitate transactions.

***

#### Use Case

A business integrating Yativo wants to enable smooth transactions on the BEP20 chain for their customers. They deposit BNB into their Gas Station wallet to ensure transactions proceed without requiring users to manage gas fees themselves. Meanwhile, they set custom fees for their platform users, which they collect separately.

For example:

* A customer initiates a transfer of a BEP20 token through the business’s platform.
* The business’s Gas Station covers the gas fees required by the blockchain.
* The business charges the customer a transaction fee that it determines (e.g., 0.1% of the transaction amount).

***

#### API Endpoints for Gas Station

**1. Create Gas Station**

* **URL:** `POST /api/v1/accounts/gas-station/create`
* **Description:** Initializes a Gas Station wallet for the business user.
* **Request Example:**
* ```json
  {
      "network": "BEP20"
  }
  ```
* **Response Example:**
* ```json
  {
      "status": "success",
      "gas_station_id": "gas123",
      "message": "Gas Station created successfully."
  }
  ```

**2. Get All Gas Stations**

* **URL:** `GET /api/v1/accounts/gas-station/all`
* **Description:** Fetches details of all Gas Stations associated with the business account.
* **Response Example:**
* ```json
  [
      {
          "gas_station_id": "gas123",
          "network": "BEP20",
          "balance": "10.5",
          "currency": "BNB"
      }
  ]
  ```

**3. Fetch Gas Station by ID**

* **URL:** `GET /api/v1/accounts/gas-station/{gas_station_id}`
* **Description:** Retrieves details of a specific Gas Station.
* **Response Example:**
* ```json
  {
      "gas_station_id": "gas123",
      "network": "BEP20",
      "balance": "10.5",
      "currency": "BNB"
  }
  ```

**4. Connect Wallet to Gas Station**

* **URL:** `POST /api/v1/accounts/gas-station/connect-wallet`
* **Description:** Connects a wallet to the Gas Station to facilitate transactions.
* **Request Example:**
* ```json
  {
      "gas_station_id": "gas123",
      "account_id": "acc456",
      "destination": "0x1234...abcd",
      "fee_type": "medium"
  }
  ```
* **Response Example:**
* ```json
  {
      "status": "success",
      "message": "Wallet connected to Gas Station successfully."
  }
  ```

**5. View Wallet Connections**

* **URL:** `POST /api/v1/accounts/gas-station/connections`
* **Description:** Fetches all wallet connections for a Gas Station.
* **Request Example:**
* ```json
  {
      "gas_station_id": "gas123"
  }
  ```
* **Response Example:**
* ```json
  [
      {
          "connection_id": "conn789",
          "account_id": "acc456",
          "destination": "0x1234...abcd",
          "fee_type": "medium"
      }
  ]
  ```

**6. Manage Gas Station Wallets**

* **Edit Connection:** Update a wallet connection to the Gas Station (`POST /api/v1/accounts/gas-station/connect-wallet/edit`).
* **Delete Connection:** Remove a wallet connection (`POST /api/v1/accounts/gas-station/connect-wallet/delete`).

***

#### Best Practices

1. **Ensure Adequate Funding**: Always maintain sufficient BNB in the Gas Station to avoid transaction delays or failures due to insufficient gas.
2. **Monitor Usage**: Use the `Get All Gas Stations` and `Fetch Gas Station by ID` endpoints to track gas usage and replenish the wallet as needed.
3. **Set Transparent Fees**: Inform end users about transaction fees you charge, ensuring transparency and compliance with local regulations.

***

#### Example Scenario

**Step-by-Step Integration:**

1. **Create a Gas Station** for the BEP20 chain using the `POST /api/v1/accounts/gas-station/create` endpoint.
2. Deposit BNB into the Gas Station wallet through your business’s admin panel.
3. Link the Gas Station to user accounts or sub-accounts via the `Connect Wallet to Gas Station` endpoint.
4. Facilitate end-user transactions without requiring them to handle gas fees directly.
5. Use the `View Wallet Connections` endpoint to monitor which wallets are linked and active.
