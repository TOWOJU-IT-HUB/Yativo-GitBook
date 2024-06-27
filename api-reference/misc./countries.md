# Countries

This endpoint is designed to provide a comprehensive list of countries along with their specific information, such as their ISO 3166-1 alpha-2 (iso2) and ISO 3166-1 alpha-3 (iso3) codes. These codes are internationally recognized and standardized representations of country names.

**What are ISO Codes?**

* **ISO 3166-1 alpha-2 (iso2) Code:** A two-letter country code (e.g., US for the United States, BR for Brazil).
* **ISO 3166-1 alpha-3 (iso3) Code:** A three-letter country code (e.g., USA for the United States, BRA for Brazil).

**Functionality**

When you access this endpoint, it will return a list of countries. Each country in the list will have associated details, primarily including:

1. **Country Name:** The official name of the country.
2. **ISO 3166-1 alpha-2 Code (iso2):** The two-letter code.
3. **ISO 3166-1 alpha-3 Code (iso3):** The three-letter code.

**Example Usage**

Here's a step-by-step explanation of how to use this endpoint and what to expect:

1. **Making the Request:**
   * You send a GET request to the endpoint URL provided by the service.
   * Example URL: `{{baseUrl}}/locations/countries`
2. **Receiving the Response:**
   * The server processes the request and responds with a JSON object.
   * This JSON object contains an array of country objects, each with details like country name, iso2, and iso3 codes.

<mark style="color:green;">`GET`</mark> `{{baseUrl}}/locations/countries`



**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |



**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 1,
            "name": "afghanistan",
            "iso2": "AF",
            "iso3": "AFG",
            "calling_code": "+93",
            "status": "active"
        },
        {
            "id": 2,
            "name": "albania",
            "iso2": "AL",
            "iso3": "ALB",
            "calling_code": "+355",
            "status": "active"
        },
        {
            "id": 3,
            "name": "algeria",
            "iso2": "DZ",
            "iso3": "DZA",
            "calling_code": "+213",
            "status": "active"
        }
    ]
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

**Detailed Breakdown of the Response**

* **countries:** An array containing objects for each country.
  * **name:** The name of the country (e.g., "Brazil").
  * **iso2:** The two-letter ISO code (e.g., "BR").
  * **iso3:** The three-letter ISO code (e.g., "BRA").
  * **calling\_code:** The country calling code

**Practical Applications**

* **Data Standardization:** Use these codes to ensure uniformity in country representation across different systems and datasets.
* **Internationalization:** Facilitate the development of applications that support multiple countries by using standardized country codes.
* **Geolocation:** Enhance location-based services by accurately identifying countries using their ISO codes.

By providing a straightforward method to retrieve and use internationally recognized country codes, this endpoint simplifies the process of handling geographical data in various applications.
