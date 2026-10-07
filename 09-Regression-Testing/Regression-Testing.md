# Games Collection - Regression Testing

## Regression Information

**Environment:** Localhost - http://localhost:3001
**Operating System:** Windows 11 Pro
**API:** RESTful API - http://localhost:3001/api
**Tool:** Postman
**Regression Status:** PASS

## Regression Testing Results

| Test Case | Regression Testing Result                                                                             | Status |
| --------- | ----------------------------------------------------------------------------------------------------- | ------ |
| TC-001    | Returned `200 OK` with game details.                                                                  | PASS   |
| TC-002    | Returned `404 Not Found` with `"error": "Game not found. ID must be greater than 0!"`.                | PASS   |
| TC-003    | Returned `404 Not Found` with `"error": "Game not found. ID must be greater than 0!"`.                | PASS   |
| TC-004    | Returned `404 Not Found` with `"error": "Game not found."`.                                           | PASS   |
| TC-005    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-006    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-007    | Returned `200 OK` and all correct games and IDs.                                                      | PASS   |
| TC-008    | Returned `200 OK` and an empty collection returned.                                                   | PASS   |
| TC-009    | Returned `201 Created` with `"status": "CREATE ENTRY SUCCESSFULLY"`.                                  | PASS   |
| TC-010    | Returned `201 Created` with `"status": "CREATE ENTRY SUCCESSFULLY"`.                                  | PASS   |
| TC-011    | Returned `400 Bad Request` with `"error": "Game name is required and cannot be empty."`.              | PASS   |
| TC-012    | Returned `400 Bad Request` with `"error": "Game name is required and cannot be empty."`.              | PASS   |
| TC-013    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-014    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-015    | Returned `200 OK` with `"status": "UPDATE ITEM SUCCESSFULLY"`.                                        | PASS   |
| TC-016    | Returned `200 OK` with `"status": "UPDATE ITEM SUCCESSFULLY"`.                                        | PASS   |
| TC-017    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-018    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-019    | Returned `404 Not Found` with `"error": "Game not found with provided ID."`.                          | PASS   |
| TC-020    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-021    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-022    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-023    | Returned `404 Not Found` with `"error": "Game not found with provided ID."`.                          | PASS   |
| TC-024    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-025    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-026    | Returned `200 OK` with `"status": "DELETE COLLECTION SUCCESSFULLY"`.                                  | PASS   |
| TC-027    | Returned `200 OK` with `"status": "DELETE COLLECTION SUCCESSFULLY"`.                                  | PASS   |

## Conclusion

Based on the regression testing results, all test cases have passed successfully, indicating that the application is functioning as expected. No new defects were identified during regression testing.

- Total Test Cases: 27
- Total Executed: 27
- Total Passed: 27
- Total Failed: 0
- Pass Percentage: 100%
- New Defects: 0
