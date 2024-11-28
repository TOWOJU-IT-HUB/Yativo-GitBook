# Assets

#### Overview

Yativo provides access to supported crypto assets, including their market prices, to enable trading, payments, or value tracking.

#### Use Case

* **Market Rates:** Use real-time prices to display crypto asset values to users.
* **Asset Listings:** Provide a dropdown of supported assets during wallet creation.

#### Endpoints

**List All Assets**

* **URL:** `GET /api/v1/assets`
* **Description:** Fetches a list of all supported assets.
* **Response Example:**
* ```json
  [
      {
          "symbol": "BTC",
          "name": "Bitcoin",
          "type": "cryptocurrency"
      },
      {
          "symbol": "ETH",
          "name": "Ethereum",
          "type": "cryptocurrency"
      }
  ]
  ```

**Get Market Prices**

* **URL:** `GET /api/v1/assets/prices`
* **Description:** Fetches the current market price of a specified asset.
* **Query Example:** `?asset_symbol=BTC`
* **Response Example:**
* ```json
  {
      "symbol": "BTC",
      "price_usd": "28000.00"
  }
  ```
* **Implementation Context:**
  * Use this endpoint to show users the equivalent value of their wallet balance in fiat currency.
  * Integrate price feeds for features like live trading or portfolio tracking.
