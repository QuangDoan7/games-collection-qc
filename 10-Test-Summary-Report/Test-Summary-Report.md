# Games Collection - Test Summary Report

## 1. Test Summary Information

**Web Application:** Games Collection
**Test Type:** Manual Functional API Testing
**Environment:** Localhost - http://localhost:3001
**Operating System:** Windows 11 Pro
**API:** RESTful API - http://localhost:3001/api
**Testing Tool:** Postman
**Final Test Status:** PASS

## 2. Testing Objective

The objective of this testing effort is to validate the functionality and reliability of the Games Collection web application through manual functional API testing using Postman. This includes verifying that all API endpoints function correctly, handling of valid and invalid inputs, and ensuring that the application meets the specified requirements.

## 3. Test Scope

### In Scope

- RESTful API
- CRUD operations
- Game data handling
- Error handling

### Out of Scope

- Performance testing
- Security penetration testing
- Load testing
- Cross-platform compatibility

## 4. Test Execution Summary

| Metric                    | Result |
| ------------------------- | ------ |
| Total Test Cases          | 27     |
| Initial Passed            | 8      |
| Initial Failed            | 19     |
| Defects Identified        | 6      |
| Defects Resolved          | 6      |
| Confirmation Tests Passed | 19     |
| Regression Tests Executed | 27     |
| Regression Tests Passed   | 27     |
| New Regression Defects    | 0      |
| Overall Test Status       | PASS   |

## 5. Defect Summary

| Defect ID | Description                                                                                                            | Severity | Priority | Final Status |
| --------- | ---------------------------------------------------------------------------------------------------------------------- | -------- | -------- | ------------ |
| BUG-001   | GET Game by ID Returns `200 OK` for a Non-existing Game                                                                | Medium   | Medium   | Closed       |
| BUG-002   | POST New Game Returns `200 OK` instead of `201 Created`                                                                | Low      | Medium   | Closed       |
| BUG-003   | POST New Game accepts Missing Required Game Name or Invalid Release Year Returns `200 OK` instead of `400 Bad Request` | Medium   | High     | Closed       |
| BUG-004   | PUT Existing Game Using Invalid Release Year Returns `200 OK` instead of `400 Bad Request`                             | Medium   | High     | Closed       |
| BUG-005   | PUT Existing Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`                            | Medium   | Medium   | Closed       |
| BUG-006   | DELETE Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`                                  | Medium   | Medium   | Closed       |

## 6. Confirmation Testing Summary

| Test Case | Confirmation Testing Result                                                                           | Status |
| --------- | ----------------------------------------------------------------------------------------------------- | ------ |
| TC-002    | Returned `404 Not Found` with `"error": "Game not found. ID must be greater than 0!"`.                | PASS   |
| TC-003    | Returned `404 Not Found` with `"error": "Game not found. ID must be greater than 0!"`.                | PASS   |
| TC-004    | Returned `404 Not Found` with `"error": "Game not found."`.                                           | PASS   |
| TC-005    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-006    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-009    | Returned `201 Created` with `"status": "CREATE ENTRY SUCCESSFULLY"`.                                  | PASS   |
| TC-010    | Returned `201 Created` with `"status": "CREATE ENTRY SUCCESSFULLY"`.                                  | PASS   |
| TC-011    | Returned `400 Bad Request` with `"error": "Game name is required and cannot be empty."`.              | PASS   |
| TC-012    | Returned `400 Bad Request` with `"error": "Game name is required and cannot be empty."`.              | PASS   |
| TC-013    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-014    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-017    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-018    | Returned `400 Bad Request` with `"error": "Release year must be a valid number and greater than 0."`. | PASS   |
| TC-019    | Returned `404 Not Found` with `"error": "Game not found with provided ID."`.                          | PASS   |
| TC-020    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-021    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-023    | Returned `404 Not Found` with `"error": "Game not found with provided ID."`.                          | PASS   |
| TC-024    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |
| TC-025    | Returned `404 Not Found` with `"error": "Game not found. ID must be numeric and greater than 0!"`.    | PASS   |

## 7. Regression Testing Summary

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

## 8. Test Closure

All planned test cases have been executed, and the results have been documented. The application has passed all regression tests, indicating that it is functioning as expected. No new defects were identified during this testing cycle. All identified defects were resolved and successfully confirmed through retesting. Therefore, the test cycle is considered complete.

## 9. Conclusion

Based on the test summary report, all test cases have been executed and passed successfully. The application has demonstrated expected behavior across all tested scenarios, and no new defects were identified. The testing objectives have been met, and the application with current RESTful API is considered stable within the tested scope.
