# Games Collection - Test Cases

## TC-001 - Retrieve an Existing Game by ID

**Related Requirement:** REQ-GAME-001
**Related Scenario:** TS-001
**Test Classification:** Positive
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains a game with ID 1.

### Test Data

- Game ID: 1

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/1`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response body contains the game with ID `1`.
- The returned game information matches the stored information for game ID `1`.

## TC-002 - Retrieve a game with ID 0

**Related Requirement:** REQ-GAME-001
**Related Scenario:** TS-002
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains only games with ID greater than 0.

### Test Data

- Game ID: 0

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/0`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body indicates that the requested game is not found.

## TC-003 - Retrieve a game using a negative ID

**Related Requirement:** REQ-GAME-001
**Related Scenario:** TS-002
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains only games with ID greater than 0.

### Test Data

- Game ID: -2

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/-2`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body indicates that the requested game is not found.

## TC-004 - Retrieve a game using a positive ID but non-existing in the collection

**Related Requirement:** REQ-GAME-001
**Related Scenario:** TS-002
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection does not contain any game with ID 77.

### Test Data

- Game ID: 77

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/77`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body does not contain any game with ID `77`.
- The response body indicates that the requested game is not found.

## TC-005 - Retrieve a game using an alphabetic ID

**Related Requirement:** REQ-GAME-001
**Related Scenario:** TS-003
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

- Game ID: abc

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/abc`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body does not contain any game with ID `abc`.
- The response body indicates that the requested game is not found.

## TC-006 - Retrieve a game using special characters in the ID

**Related Requirement:** REQ-GAME-001
**Related Scenario:** TS-003
**Test Classification:** Negative
**Test Technique:** Error Guessing

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

- Game ID: !@#

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api/!@#`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body does not contain any game with ID `!@#`.
- The response body indicates that the requested game is not found.

## TC-007 - Retrieve all games in the collection

**Related Requirement:** REQ-GAME-002
**Related Scenario:** TS-004
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains one or more games.

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response body contains all games currently stored in the collection.

## TC-008 - Retrieve all games in an empty collection

**Related Requirement:** REQ-GAME-002
**Related Scenario:** TS-005
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection is empty.

### Test Steps

1. Open Postman.
2. Select the GET method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response body returns an empty collection.
- No game data is returned.

## TC-009 - Add a new game with all fields populated

**Related Requirement:** REQ-GAME-003, REQ-VAL-001
**Related Scenario:** TS-006
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

```json
{
  "game": "Onimusha - Way of the sword",
  "platform": "PlayStation 5, Nintendo Switch 2, Xbox Series X and Series S, GeForce Now, Microsoft Windows",
  "releaseYear": 2026,
  "genre": "Action-adventure, Fighting, Role-playing",
  "publisher": "Capcom"
}
```

### Test Steps

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `201 Created`.
- The response indicates that the game is successfully added.
- A new game containing the submitted information is added to the collection.

## TC-010 - Add a new game with at least one field empty, except game name

**Related Requirement:** REQ-GAME-003, REQ-VAL-001
**Related Scenario:** TS-007
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

```json
{
  "game": "Asura's Wrath",
  "platform": "PlayStation 3",
  "releaseYear": 2012,
  "publisher": "Capcom"
}
```

### Test Steps

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `201 Created`.
- The response indicates that the game is successfully added.
- A new game containing the submitted information is added to the collection.

## TC-011 - Add a new game with empty game name

**Related Requirement:** REQ-GAME-003, REQ-VAL-001
**Related Scenario:** TS-007
**Test Classification:** Negative
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

```json
{
  "platform": "PlayStation 1",
  "releaseYear": 1999,
  "genre": "Action-adventure",
  "publisher": "Square Enix"
}
```

### Test Steps

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `400 Bad Request`.
- The response indicates that the game name is required.
- The game is not added to the collection.

## TC-012 - Add a new game with all fields empty

**Related Requirement:** REQ-GAME-003, REQ-VAL-001
**Related Scenario:** TS-008
**Test Classification:** Negative
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

```json
{}
```

### Test Steps

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. Enter an empty JSON object {} in the request body.
6. Send the request.

### Expected Result

- The API returns HTTP status code `400 Bad Request`.
- The response indicates that the game name is required.
- The game is not added to the collection.

## TC-013 - Add a new game with alphabetic data for the Release Year

**Related Requirement:** REQ-GAME-003, REQ-VAL-002
**Related Scenario:** TS-009
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

```json
{
  "game": "Chrono Trigger",
  "platform": "PlayStation 1",
  "releaseYear": "abcd",
  "genre": "Action-adventure",
  "publisher": "Square Enix"
}
```

### Test Steps

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with a non-numeric release year.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `400 Bad Request`.
- The response indicates that the release year must contain numeric data.
- The game is not added to the collection.

## TC-014 - Add a new game with special characters for the Release Year

**Related Requirement:** REQ-GAME-003, REQ-VAL-002
**Related Scenario:** TS-009
**Test Classification:** Negative
**Test Technique:** Error Guessing

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

```json
{
  "game": "Chrono Trigger",
  "platform": "PlayStation 1",
  "releaseYear": "@#$%",
  "genre": "Action-adventure",
  "publisher": "Square Enix"
}
```

### Test Steps

1. Open Postman.
2. Select the POST method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with a release year containing special characters.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `400 Bad Request`.
- The response indicates that the release year must contain numeric data.
- The game is not added to the collection.

## TC-015 - Edit an existing game successfully with at least one field updated

**Related Requirement:** REQ-GAME-004
**Related Scenario:** TS-010
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains an existing game added recently with ID 6.

### Test Data

- Field being updated: `platform` - removing `Geforce Now`

```json
{
  "game": "Onimusha - Way of the sword",
  "platform": "PlayStation 5, Nintendo Switch 2, Xbox Series X and Series S, Microsoft Windows",
  "releaseYear": 2026,
  "genre": "Action-adventure, Fighting, Role-playing",
  "publisher": "Capcom"
}
```

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/6`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with the updated platform value.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response indicates that the game is successfully updated.
- The specified field for game ID `6` is updated with the new value.
- The other fields remain unchanged.

## TC-016 - Edit an existing game successfully with all fields updated

**Related Requirement:** REQ-GAME-004
**Related Scenario:** TS-011
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains an existing game added recently with ID 6.

### Test Data

- All fields are being updated

```json
{
  "game": "Onimusha - Dawn of Dreams",
  "platform": "PlayStation 2",
  "releaseYear": 2006,
  "genre": "Action-adventure, Role-playing",
  "publisher": "Capcommmmmmm"
}
```

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/6`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with all updated field values.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response indicates that the game is successfully updated.
- All fields for game ID `6` are updated with the new values.

## TC-017 - Edit an existing game using alphabetic data for the Release Year

**Related Requirement:** REQ-GAME-004, REQ-VAL-002
**Related Scenario:** TS-012
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains an existing game recently added with ID 6.

### Test Data

- Field being updated: `releaseYear`

```json
{
  "game": "Onimusha - Dawn of Dreams",
  "platform": "PlayStation 2",
  "releaseYear": "abc",
  "genre": "Action-adventure, Role-playing",
  "publisher": "Capcommmmmmm"
}
```

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/6`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with an alphabetic data for the Release Year.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `400 Bad Request`.
- The response indicates that the Release Year must contain numeric data.
- The game with ID `6` is not updated.

## TC-018 - Edit an existing game using special characters for the Release Year

**Related Requirement:** REQ-GAME-004, REQ-VAL-002
**Related Scenario:** TS-012
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains an existing game recently added with ID 6.

### Test Data

- Field being updated: `releaseYear`

```json
{
  "game": "Onimusha - Dawn of Dreams",
  "platform": "PlayStation 2",
  "releaseYear": "@#$%",
  "genre": "Action-adventure, Role-playing",
  "publisher": "Capcommmmmmm"
}
```

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/6`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with special characters for the Release Year.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `400 Bad Request`.
- The response indicates that the Release Year must contain numeric data.
- The game with ID `6` is not updated.

## TC-019 - Edit a game using a positive ID but non-existing in the collection

**Related Requirement:** REQ-GAME-004
**Related Scenario:** TS-013
**Test Classification:** Negative
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection does not contain any game with ID 77.

### Test Data

- ID: 77

```json
{
  "game": "Test Game",
  "platform": "Test Platform",
  "releaseYear": 2026,
  "genre": "Test Genre",
  "publisher": "Test Publisher"
}
```

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/77`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response body indicates that the requested game is not found.
- No game is updated or created.

## TC-020 - Edit a game using an alphabetic ID

**Related Requirement:** REQ-GAME-004
**Related Scenario:** TS-014
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

- ID: abc

```json
{
  "game": "Test Game",
  "platform": "Test Platform",
  "releaseYear": 2026,
  "genre": "Test Genre",
  "publisher": "Test Publisher"
}
```

- game: Test Game
- platform: Test Platform
- releaseYear: 2026
- genre: Test Genre
- publisher: Test Publisher

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/abc`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with an alphabetic ID for attempting to edit a game.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response indicates that there is no game found.
- No game is updated or created.

## TC-021 - Edit a game using a special character ID

**Related Requirement:** REQ-GAME-004
**Related Scenario:** TS-014
**Test Classification:** Negative
**Test Technique:** Error Guessing

### Preconditions

- RESTful API server is running.
- The test database is available.

### Test Data

- ID: !@#

```json
{
  "game": "Test Game",
  "platform": "Test Platform",
  "releaseYear": 2026,
  "genre": "Test Genre",
  "publisher": "Test Publisher"
}
```

### Test Steps

1. Open Postman.
2. Select the PUT method.
3. Enter the endpoint `http://localhost:3001/api/!@#`.
4. Select **Body -> raw -> JSON**.
5. Enter the test data in the request body with a special character ID for attempting to edit a game.
6. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response indicates that no game is found for editing.
- No game is updated or created.

## TC-022 - Delete an existing game in the collection.

**Related Requirement:** REQ-GAME-005
**Related Scenario:** TS-015
**Test Classification:** Positive
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains an existing game recently added with ID 6.

### Test Data

- ID: 6

### Test Steps

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api/6`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response indicates the game is deleted successfully.
- The game with ID 6 is no longer present in the collection.

## TC-023 - Delete a game using a positive ID but non-existing in the collection.

**Related Requirement:** REQ-GAME-005
**Related Scenario:** TS-016
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection does not contain any game with ID 99.

### Test Data

- ID: 99

### Test Steps

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api/99`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response indicates that the requested game is not found.
- No game is deleted.
- The collection remains unchanged.

## TC-024 - Delete a game using a alphabetic ID.

**Related Requirement:** REQ-GAME-005
**Related Scenario:** TS-017
**Test Classification:** Negative
**Test Technique:** Equivalence Partitioning

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains one or more games.

### Test Data

- ID: abc

### Test Steps

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api/abc`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response indicates that the requested game is not found due to the alphabetic ID.
- No game is deleted.
- The collection remains unchanged.

## TC-025 - Delete a game using a special character ID.

**Related Requirement:** REQ-GAME-005
**Related Scenario:** TS-017
**Test Classification:** Negative
**Test Technique:** Error Guessing

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains one or more games.

### Test Data

- ID: !@#

### Test Steps

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api/!@#`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `404 Not Found`.
- The response indicates that the requested game is not found due to the special character ID.
- No game is deleted.
- The collection remains unchanged.

## TC-026 - Delete all games in the collection.

**Related Requirement:** REQ-GAME-006
**Related Scenario:** TS-018
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection contains one or more games.

### Test Steps

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Send the request.

### Expected Result

- The API returns the expected success HTTP status code `200 OK`.
- The response indicates all games were deleted successfully.
- The collection is empty after the deletion.

## TC-027 - Delete all games with empty collection.

**Related Requirement:** REQ-GAME-006
**Related Scenario:** TS-019
**Test Classification:** Positive
**Test Technique:** N/A

### Preconditions

- RESTful API server is running.
- The test database is available.
- The collection is empty.

### Test Steps

1. Open Postman.
2. Select the DELETE method.
3. Enter the endpoint `http://localhost:3001/api`.
4. Send the request.

### Expected Result

- The API returns the HTTP status code `200 OK`.
- The response indicates that there are no games to delete.
- The collection remains empty.
