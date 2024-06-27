# Virtual Cards

### Customer Registration for Virtual Card Creation

Before a customer can create a virtual card, they must be registered and activated for this service. This registration involves providing specific information and completing an activation request through the endpoint `{{baseUrl}}/customer/virtual/cards/activate`. Below are the necessary details and steps for this process.



We support all countries and have different IDType for certain countries; here is the list;

| Countries       | Accepted Documents                              |
| --------------- | ----------------------------------------------- |
| Nigeria         | \[`vNIN`, `PASSPORT`, `DRIVERS_LICENSE`, `PVC`] |
| Ghana           | \[`PASSPORT`, `DRIVERS_LICENSE`, `VOTERS_ID`]   |
| Kenya           | \[`PASSPORT`, `NATIONAL_ID`]                    |
| Senegal         | \[`NATIONAL_ID, ECOWAS_ID`]                     |
| Other Countries | \[`NATIONAL_ID`]                                |

#### Required Information for Registration

To register a customer for virtual card creation, the following information is needed:

* **customerId**: Unique identifier for the customer.
* **customerEmail**: Customer's email address.
* **idNumber**: Identification number of the customer.
* **idType**: Type of identification (e.g., passport, driver's license).
* **firstName**: Customer's first name.
* **dateOfBirth:** Customer's date of birth.
* **lastName**: Customer's last name.
* **phoneNumber**: Customer's phone number.
* **city**: City of residence.
* **state**: State of residence.
* **country**: Country of residence in ISO3.
* **zipCode**: Postal code.
* **line1**: Address line 1.
* **houseNumber**: House or apartment number.
* **idImage**: URL of Image of the identification document.

#### Activation Request Process

1. **Collect Customer Information**: Gather all the required information listed above from the customer.
2. **Send Activation Request**: Make a POST request to the endpoint `api/v1/customer/virtual/cards/activate` with the collected information in the request payload.

#### Example Request Payload

Here is an example of how the request payload should be structured:

```json
{
  "customerId": "123456789",
  "customerEmail": "customer@example.com",
  "idNumber": "A12345678",
  "idType": "passport",
  "firstName": "John",
  "lastName": "Doe",
  "dateOfBirth": "YYYY-MM-DD",
  "phoneNumber": "+1234567890",
  "city": "New York",
  "state": "NY",
  "country": "USA",
  "zipCode": "10001",
  "line1": "123 Main St",
  "houseNumber": "456",
  "idImage": "https://example.com/id_image.jpg"
}

```

#### Example Response

Upon successful activation, the API will respond with a confirmation message and status code. Here is an example response:

```json
{
  "status": "success",
  "message": "Virtual card service activated successfully.",
  "activationDate": "2024-05-29T12:34:56Z"
}
```

#### Important Considerations

* **Data Validation**: Ensure all provided information is accurate and valid. Incorrect details may result in activation failure.
* **Security**: Securely handle all customer data, especially sensitive information such as the ID image and personal identifiers. Use encryption and secure communication protocols.
* **Eligibility Checks**: The system may perform additional checks to verify the customer's eligibility for virtual card activation. This might include KYC compliance, account status verification, and fraud prevention measures.

By following these steps and ensuring all necessary information is correctly provided, customers can be successfully registered and activated for virtual card creation.
