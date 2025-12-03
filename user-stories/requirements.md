# Technical Requirement Specifications

## 1. User Authentication Feature
**Description:** Allow users to register and log in to the system.
* **API Endpoint:** `POST /api/v1/auth/register`
* **Input (JSON):**
    ```json
    {
      "email": "user@example.com",
      "password": "securePassword123",
      "first_name": "John",
      "last_name": "Doe"
    }
    ```
* **Output (Success 201 Created):**
    ```json
    {
      "user_id": "uuid-string",
      "email": "user@example.com",
      "created_at": "timestamp"
    }
    ```
* **Validation Rules:**
    * Email must be valid format (regex).
    * Password must be at least 8 characters.
    * Email must be unique in the database.

## 2. Property Management Feature
**Description:** Allow hosts to create new property listings.
* **API Endpoint:** `POST /api/v1/places`
* **Input (JSON):**
    ```json
    {
      "name": "Cozy Apartment",
      "description": "A nice place in the city center",
      "number_rooms": 2,
      "number_bathrooms": 1,
      "max_guest": 4,
      "price_by_night": 120,
      "latitude": 30.0444,
      "longitude": 31.2357
    }
    ```
* **Output (Success 201 Created):** Returns the `place_id` and full object.
* **Requirements:**
    * User must be authenticated.
    * `price_by_night` must be a positive integer.

## 3. Booking Feature
**Description:** Handle reservation of properties.
* **API Endpoint:** `POST /api/v1/places/{place_id}/book`
* **Input (JSON):**
    ```json
    {
      "user_id": "uuid-string",
      "check_in": "2025-12-01",
      "check_out": "2025-12-05"
    }
    ```
* **Output (Success 200 OK):** Booking confirmation details.
* **Logic:**
    * System must query `Booking` table to ensure no overlap for `{place_id}` during the requested dates.
    * If overlap exists, return `409 Conflict`.
