# States

#### Endpoint for Retrieving State Information

**Endpoint**

`/locations/states/{{state-id}}`

This endpoint allows you to retrieve detailed information about specific states within a country. By providing the `state-id`, you can access a list of states along with their relevant details.

**Example Request**

* **URL:** `{{baseUrl}}/locations/states/{{state-id}}`
* **Method:** GET

**Response Structure**

When you make a request to this endpoint, you will receive a JSON response with the following structure:

```json
{
    "status": "success",
    "status_code": 200,
    "message": "Request successful",
    "data": [
        {
            "id": 2647,
            "country_id": 160,
            "name": "abia",
            "status": "active",
            "country": {
                "id": 160,
                "name": "nigeria",
                "iso2": "NG",
                "iso3": "NGA",
                "calling_code": "+234",
                "status": "active"
            }
        },
        {
            "id": 2648,
            "country_id": 160,
            "name": "abuja federal capital territory",
            "status": "active",
            "country": {
                "id": 160,
                "name": "nigeria",
                "iso2": "NG",
                "iso3": "NGA",
                "calling_code": "+234",
                "status": "active"
            }
        }
    ]
}
```

**Detailed Breakdown of the Response**

* **status:** A string indicating the result of the request (e.g., "success").
* **status\_code:** A numerical code representing the HTTP status (e.g., 200 for a successful request).
* **message:** A descriptive message about the request status (e.g., "Request successful").
* **data:** An array containing state objects with the following details:
  * **id:** The unique identifier for the state (e.g., 2647).
  * **country\_id:** The unique identifier for the country the state belongs to (e.g., 160).
  * **name:** The name of the state (e.g., "abia").
  * **status:** The status of the state (e.g., "active").
  * **country:** An object containing details about the country:
    * **id:** The unique identifier for the country (e.g., 160).
    * **name:** The name of the country (e.g., "nigeria").
    * **iso2:** The ISO 3166-1 alpha-2 code for the country (e.g., "NG").
    * **iso3:** The ISO 3166-1 alpha-3 code for the country (e.g., "NGA").
    * **calling\_code:** The international calling code for the country (e.g., "+234").
    * **status:** The status of the country (e.g., "active").

This detailed response ensures that you receive comprehensive information about states and their associated countries, enabling you to manage and utilize geographical data effectively.
