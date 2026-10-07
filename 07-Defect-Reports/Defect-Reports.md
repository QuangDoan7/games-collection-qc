# Games Collection - Defect Reports

## BUG-001 - GET Game by ID Returns `200 OK` for a Non-existing Game

**Related Test Cases:** TC-002, TC-003, TC-004, TC-005, TC-006
**Severity:** Medium // This defect affects the correctness of the API response for non-existing games.
**Priority:** Medium // The priority is set to medium as it impacts the API's correctness but does not block functionality.
**Status:** Open

### Description

When retrieving a game by its ID that does not exist in the collection, the API incorrectly returns a `200 OK` status instead of a `404 Not Found` status.

### Preconditions

- RESTful API server is running.
- The test database is available.
- The requested Game ID does not exist in the collection.

### Steps to Reproduce

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/{id}`. Replace `{id}` with the test Game ID.
4. Append a non-existing Game ID to the endpoint according to the test case.

- TC-002: ID `0`
- TC-003: ID `-2`
- TC-004: ID `77`
- TC-005: ID `abc`
- TC-006: ID `!@#`

5. Send the GET request.
6. Observe the response status code.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body indicates `"error": "Game not found"`.

### Actual Result

- The API returns the HTTP status code `200 OK`.
- The response body correctly indicates `"error": "Game not found"`.

## BUG-002 - POST New Game Returns `200 OK` instead of `201 Created`

**Related Test Cases:** TC-009, TC-010
**Severity:** Low // This defect has a minor impact on the API's behavior as it only affects the status code returned for successful POST requests.
**Priority:** Medium // The priority is set to medium as it does not block functionality but should be corrected for proper API behavior.
**Status:** Open

### Description

When adding a new game to the collection successfully, the API incorrectly returns a `200 OK` status instead of a `201 Created` status.

### Preconditions

- RESTful API server is running.
- The test database is available.

### Steps to Reproduce

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. In the request body, provide the details of the new game according to the test case.

- TC-009: Provide game details with information as follows:

```json
{
  "game": "Onimusha - Way of the sword",
  "platform": "PlayStation 5, Nintendo Switch 2, Xbox Series X and Series S, GeForce Now, Microsoft Windows",
  "releaseYear": 2026,
  "genre": "Action-adventure, Fighting, Role-playing",
  "publisher": "Capcom"
}
```

TC-010: Provide game details with information as follows:

```json
{
  "game": "Asura's Wrath",
  "platform": "PlayStation 3",
  "releaseYear": 2012,
  "publisher": "Capcom"
}
```

6. Send the POST request.
7. Observe the response status code and response body.

### Expected Result

- The API returns the HTTP status code `201 Created`.
- The response indicates that the game is successfully added.
- A new game containing the submitted information is added to the collection.

### Actual Result

- The API returns the HTTP status code `200 OK`.
- The response indicates that the game is successfully added as `"status": "CREATE ENTRY SUCCESSFUL"`.
- The game is added to the collection successfully, but the status code is incorrect.

## BUG-003 - POST New Game Accepts Missing Required Game Name or Invalid Release Year and Returns `200 OK` instead of `400 Bad Request`

**Related Test Cases:** TC-011, TC-012, TC-013, TC-014
**Severity:** Medium // This defect affects the API's validation logic for required fields and data types.
**Priority:** High // This defect should be addressed promptly due to its impact on data integrity.
**Status:** Open

### Description

When attempting to add a new game with a missing required game name or an invalid non-numeric Release Year, the API accepts the request and adds the invalid game to the collection instead of rejecting the request with 400 Bad Request.

### Preconditions

- RESTful API server is running.
- The test database is available.

### Steps to Reproduce

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. In the request body, provide the details of the new game according to the test case.

- TC-011: Provide game details with missing game name field.

```json
{
  "platform": "PlayStation 1",
  "releaseYear": 1999,
  "genre": "Action-adventure",
  "publisher": "Square Enix"
}
```

- TC-012: Provide game details with all fields empty.

```json
{}
```

- TC-013: Provide game details with alphabetic data for the Release Year field.

```json
{
  "game": "Chrono Trigger",
  "platform": "PlayStation 1",
  "releaseYear": "abcd",
  "genre": "Action-adventure",
  "publisher": "Square Enix"
}
```

- TC-014: Provide game details with special characters in the Release Year field.

```json
{
  "game": "Chrono Trigger",
  "platform": "PlayStation 1",
  "releaseYear": "@#$%",
  "genre": "Action-adventure",
  "publisher": "Square Enix"
}
```

6. Send the POST request.
7. Observe the response status code and response body.

### Expected Result

- The API returns the HTTP status code `400 Bad Request`.
- The response indicates the applicable validation errors:
  - For TC-011: Game name is required when the game name is missing.
  - For TC-012: Release must be numeric when a non-numeric value is provided.
- The game is not added to the collection.

### Actual Result

- The API returns the HTTP status code `200 OK`.
- The response indicates that the game is successfully added as `"status": "CREATE ENTRY SUCCESSFUL"`.
- The game is added to the collection despite the missing or invalid field values, and the status code is incorrect.

## BUG-004 - PUT Existing Game Using Invalid Release Year Returns `200 OK` instead of `400 Bad Request`

**Related Test Cases:** TC-017, TC-018
**Severity:** Medium // This defect affects the API's validation logic for the Release Year field.
**Priority:** High // This defect should be addressed promptly due to its impact on data integrity.
**Status:** Open

### Description

The API allows updating an existing game with an invalid Release Year value, such as alphabetic characters or special symbols. Instead of returning a `400 Bad Request` response, the API returns `200 OK` and indicates that the update was successful. This behavior violates the expected validation rules for the Release Year field and can lead to incorrect data being stored in the database.

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains a recently added game with ID `6`.

### Steps to Reproduce

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/{id}`, replacing `{id}` with the ID of the game you want to update. E.g.: The game was recently added succuessfully with game ID `6`.
4. Select **Body -> raw -> JSON**.
5. In the request body, provide the details of the new information for the game according to the test case.

- TC-017: Update an existing game with alphabetic data in the Release Year field.

```json
{
  "game": "Onimusha - Way of the sword",
  "platform": "PlayStation 5, Nintendo Switch 2, Xbox Series X and Series S, GeForce Now, Microsoft Windows",
  "releaseYear": "abc",
  "genre": "Action-adventure, Fighting, Role-playing",
  "publisher": "Capcom"
}
```

- TC-018: Update an existing game with special characters in the Release Year field.

```json
{
  "game": "Onimusha - Way of the sword",
  "platform": "PlayStation 5, Nintendo Switch 2, Xbox Series X and Series S, GeForce Now, Microsoft Windows",
  "releaseYear": "!@#",
  "genre": "Action-adventure, Fighting, Role-playing",
  "publisher": "Capcom"
}
```

6. Send the PUT request.
7. Observe the response status code and response body.

### Expected Result

- The API should return the HTTP status code `400 Bad Request`.
- The response indicates that the Release Year field must contain numeric data.
- The game with ID `6` is not updated.

### Actual Result

- The API returns the HTTP status code `200 OK`.
- The response indicates that the game was successfully updated despite the invalid Release Year value.
- The game with ID `6` is updated in the collection.

## BUG-005 - PUT Existing Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`

**Related Test Cases:** TC-019, TC-020, TC-021
**Severity:** Medium // This defect affects the API's handling of invalid or non-existing IDs.
**Priority:** Medium // This defect affects the API's handling of invalid or non-existing IDs.
**Status:** Open

### Description

When attempting to update a game using an invalid or non-existing ID, the API returns a `200 OK` status code instead of the expected `404 Not Found`. This behavior can lead to confusion and incorrect assumptions about the existence of the game in the collection.

### Preconditions

- RESTful API server is running.
- The test database is available.
- The requested Game ID does not correspond to an existing game in the collection.

### Steps to Reproduce

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/{id}`, replacing `{id}` with the invalid or non-existing ID you want to test.

- TC-019: Edit a game using a positive ID that does not exist in the collection - E.g.: ID ``77` - Endpoint: `http://localhost:3001/api/77`

- TC-020: Edit a game using an alphabetic ID that does not exist in the collection. E.g.: ID `abc` - Endpoint: `http://localhost:3001/api/abc`

- TC-021: Edit a game using a special character ID that does not exist in the collection. E.g.: ID `!@#` - Endpoint: `http://localhost:3001/api/!@#`

4. Select **Body -> raw -> JSON**.
5. In the request body, provide the details of the new information for the game according to the test case.

```json
{
  "game": "Test Edit Game",
  "platform": "Test Platform",
  "releaseYear": 2026,
  "genre": "Test Genre",
  "publisher": "Test Publisher"
}
```

6. Send the PUT request.
7. Observe the response status code and response body.

### Expected Result

- The API should return the HTTP status code `404 Not Found`.
- The response indicates that the requested game is not found.
- No game is added or updated in the collection.

### Actual Result

- The API returns the HTTP status code `200 OK`.
- The response body indicates `"status": "UPDATE ITEM SUCCESSFUL"`.
- No game matching the requested ID exists in the collection, but the API reports the update as successful.
- No game is actually updated or added in the collection.

## BUG-006 - DELETE Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`

**Related Test Cases:** TC-023, TC-024, TC-025
**Severity:** Medium // This defect affects the API's handling of invalid or non-existing IDs.
**Priority:** Medium // This defect affects the API's handling of invalid or non-existing IDs.
**Status:** Open

### Description

When attempting to delete a game using an invalid or non-existing ID, the API returns a `200 OK` status code instead of the expected `404 Not Found`. This behavior can lead to confusion and incorrect assumptions about the existence of the game in the collection.

### Preconditions

- RESTful API server is running.
- The test database is available.
- The requested Game ID does not correspond to an existing game in the collection.

### Steps to Reproduce

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api/{id}`, replacing `{id}` with the invalid or non-existing ID you want to test.

- TC-023: Delete a game using a positive ID that does not exist in the collection - E.g.: ID `77` - Endpoint: `http://localhost:3001/api/77`

- TC-024: Delete a game using an alphabetic ID that does not exist in the collection - E.g.: ID `abc` - Endpoint: `http://localhost:3001/api/abc`

- TC-025: Delete a game using a special character ID that does not exist in the collection - E.g.: ID `!@#` - Endpoint: `http://localhost:3001/api/!@#`

4. Send the DELETE request.
5. Observe the response status code and response body.

### Expected Result

- The API should return the HTTP status code `404 Not Found`.
- The response indicates that the requested game is not found.
- No game is deleted from the collection.
- The collection remains unchanged.

### Actual Result

- The API returns the HTTP status code `200 OK`, instead of the expected `404 Not Found`.
- The response body indicates `"status": "DELETE ITEM SUCCESSFUL"`, even though no game matching the requested ID exists in the collection.
- The collection remains unchanged, despite the API indicating a successful deletion.
