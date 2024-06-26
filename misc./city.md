# City

#### Endpoint for Retrieving City Information

**Endpoint**

`/locations/cities/{{state_id}}`

This endpoint allows you to retrieve detailed information about specific cities within a state. By providing the `state_id`, you can access a list of cities along with their relevant details.

**Example Request**

* **URL:** `{{baseUrl}}/locations/cities/{{state_id}}`
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
            "id": 708,
            "state_id": 11,
            "name": "aldona",
            "status": "active",
            "state": {
                "id": 11,
                "country_id": 101,
                "name": "goa",
                "status": "active"
            }
        },
        {
            "id": 709,
            "state_id": 11,
            "name": "altinho",
            "status": "active",
            "state": {
                "id": 11,
                "country_id": 101,
                "name": "goa",
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
* **data:** An array containing city objects with the following details:
  * **id:** The unique identifier for the city (e.g., 708).
  * **state\_id:** The unique identifier for the state the city belongs to (e.g., 11).
  * **name:** The name of the city (e.g., "aldona").
  * **status:** The status of the city (e.g., "active").
  * **state:** An object containing details about the state:
    * **id:** The unique identifier for the state (e.g., 11).
    * **country\_id:** The unique identifier for the country the state belongs to (e.g., 101).
    * **name:** The name of the state (e.g., "goa").
    * **status:** The status of the state (e.g., "active").

This detailed response ensures that you receive comprehensive information about cities and their associated states, enabling you to manage and utilize geographical data effectively.
