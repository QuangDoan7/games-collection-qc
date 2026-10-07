# Games Collection - Confirmation Test Results

## Confirmation Test Information

**Environment:** Localhost - http://localhost:3001
**Operating System:** Windows 11 Pro
**API:** RESTful API - http://localhost:3001/api
**Tool:** Postman

## BUG-001 - GET Game by ID Returns `200 OK` for a Non-existing Game

**Related Test cases:** TC-002, TC-003, TC-004, TC-005, TC-006
**Confirmation Test Status:** PASS

### Confirmation Test Results

| Test Case | Retest Result                                                                                      | Status |
| --------- | -------------------------------------------------------------------------------------------------- | ------ |
| TC-002    | Returned `404 Not Found` with `"error": "Game not found. ID must be greater than 0!"`.             | PASS   |
| TC-003    | Returned `404 Not Found` with `"error": "Game not found. ID must be greater than 0!"`.             | PASS   |
| TC-004    | Returned `404 Not Found` with `"error": "Game not found."`.                                        | PASS   |
| TC-005    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`. | PASS   |
| TC-006    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`. | PASS   |

### Conclusion

BUG-001 was successfully fixed. All related failed test cases passed during confirmation testing.

## BUG-002 - POST New Game Returns `200 OK` instead of `201 Created`

**Related Test cases:** TC-009, TC-010
**Confirmation Test Status:** PASS

### Confirmation Test Results

| Test Case | Confirmation Test Result                                             | Status |
| --------- | -------------------------------------------------------------------- | ------ |
| TC-009    | Returned `201 Created` with `"status": "CREATE ENTRY SUCCESSFULLY"`. | PASS   |
| TC-010    | Returned `201 Created` with `"status": "CREATE ENTRY SUCCESSFULLY"`. | PASS   |

### Conclusion

BUG-002 was successfully fixed. All related failed test cases passed during confirmation testing.

## BUG-003 - POST New Game Accepts Missing Required Game Name or Invalid Release Year and Returns `200 OK` instead of `400 Bad Request`

**Related Test cases:** TC-011, TC-012, TC-013, TC-014
**Confirmation Test Status:** PASS

### Confirmation Test Results

| Test Case | Confirmation Test Result                                                                              | Status |
| --------- | ----------------------------------------------------------------------------------------------------- | ------ |
| TC-011    | Returned `400 Bad Request` with `"error": "Game name is required and cannot be empty."`.              | PASS   |
| TC-012    | Returned `400 Bad Request` with `"error": "Game name is required and cannot be empty."`.              | PASS   |
| TC-013    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-014    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |

### Conclusion

BUG-003 was successfully fixed. All related failed test cases passed during confirmation testing.

## BUG-004 - PUT Existing Game Using Invalid Release Year Returns `200 OK` instead of `400 Bad Request`

**Related Test cases:** TC-017, TC-018
**Confirmation Test Status:** PASS

### Confirmation Test Results

| Test Case | Confirmation Test Result                                                                              | Status |
| --------- | ----------------------------------------------------------------------------------------------------- | ------ |
| TC-017    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-018    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |

### Conclusion

BUG-004 was successfully fixed. All related failed test cases passed during confirmation testing.

## BUG-005 - PUT Existing Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`

**Related Test cases:** TC-019, TC-020, TC-021
**Confirmation Test Status:** PASS

### Confirmation Test Results

| Test Case | Confirmation Test Result                                                                           | Status |
| --------- | -------------------------------------------------------------------------------------------------- | ------ |
| TC-019    | Returned `404 Not Found` with `"error": "Game not found with provided ID."`.                       | PASS   |
| TC-020    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`. | PASS   |
| TC-021    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`. | PASS   |

### Conclusion

BUG-005 was successfully fixed. All related failed test cases passed during confirmation testing.

## BUG-006 - DELETE Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`

**Related Test cases:** TC-023, TC-024, TC-025
**Confirmation Test Status:** PASS

### Confirmation Test Results

| Test Case | Confirmation Test Result                                                                           | Status |
| --------- | -------------------------------------------------------------------------------------------------- | ------ |
| TC-023    | Returned `404 Not Found` with `"error": "Game not found with provided ID."`.                       | PASS   |
| TC-024    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`. | PASS   |
| TC-025    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`. | PASS   |

### Conclusion

BUG-006 was successfully fixed. All related failed test cases passed during confirmation testing.
