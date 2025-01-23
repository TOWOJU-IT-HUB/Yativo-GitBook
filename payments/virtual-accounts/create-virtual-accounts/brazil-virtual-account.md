# Brazil PIX QR

**Availability**

This service is exclusively available for users in Brazil who have completed and approved [KYC](../../../compliance/verification/) profiles.

PIX is an instant payment service created by [Banco Central do Brasil (BCB)](https://www.bcb.gov.br/en/financialstability/pix_en)

**Features**

* **Money Transfers:** You can  receive money directly using your PIX QR.

**Payment Processing**

Users can receive payments through Brazil's local ACH network using PIX, a widely-used instant payment system. Here's how it works:

1. **Payment Reception:** When a payment is received through PIX, Yativo will process it.
2. **Notification:** Yativo will send a notification to the URL you have configured as a callback. This ensures you are promptly informed of any incoming funds.
3. **Callback Format:** The format of these notifications can be checked in the Callback Virtual Account documentation.

**Example Request**

```
POST {{baseUrl}}/business/virtual-account/create
Content-Type: application/json

{
    "customer_id": "123e4567-e89b-12d3-a456-426614174000",
    "currency": "BRL"
}
```
