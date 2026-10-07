# Games Collection - Test Execution Results

## Test Execution Information

**Environment:** Localhost - http://localhost:3001
**Operating System:** Windows 11 Pro
**API:** RESTful API - http://localhost:3001/api
**Tool:** Postman

## Test Execution Results

| Test Case | Actual Result                                                                                                              | Status | Defect ID |
| --------- | -------------------------------------------------------------------------------------------------------------------------- | ------ | --------- |
| TC-001    | Returned `200 OK` and the correct game with ID `1`.                                                                        | PASS   | N/A       |
| TC-002    | Returned `200 OK` instead of expected `404 Not Found`; response correctly indicated `"error": "Game not found"`.           | FAIL   | BUG-001   |
| TC-003    | Returned `200 OK` instead of expected `404 Not Found`; response correctly indicated `"error": "Game not found"`.           | FAIL   | BUG-001   |
| TC-004    | Returned `200 OK` instead of expected `404 Not Found`; response correctly indicated `"error": "Game not found"`.           | FAIL   | BUG-001   |
| TC-005    | Returned `200 OK` instead of expected `404 Not Found`; response correctly indicated `"error": "Game not found"`.           | FAIL   | BUG-001   |
| TC-006    | Returned `200 OK` instead of expected `404 Not Found`; response correctly indicated `"error": "Game not found"`.           | FAIL   | BUG-001   |
| TC-007    | Returned `200 OK` and all correct games and IDs.                                                                           | PASS   | N/A       |
| TC-008    | Returned `200 OK` and an empty collection returned.                                                                        | PASS   | N/A       |
| TC-009    | Returned `200 OK` instead of expected `201 Created`; response correctly indicated `"status": "CREATE ENTRY SUCCESSFULLY"`. | FAIL   | BUG-002   |
| TC-010    | Returned `200 OK` instead of expected `201 Created`; response correctly indicated `"status": "CREATE ENTRY SUCCESSFULLY"`. | FAIL   | BUG-002   |
| TC-011    | Returned `200 OK` instead of expected `400 Bad Request`; response returned `"status": "CREATE ENTRY SUCCESSFULLY"`.        | FAIL   | BUG-003   |
| TC-012    | Returned `200 OK` instead of expected `400 Bad Request`; response returned `"status": "CREATE ENTRY SUCCESSFULLY"`.        | FAIL   | BUG-003   |
| TC-013    | Returned `200 OK` instead of expected `400 Bad Request`; response returned `"status": "CREATE ENTRY SUCCESSFULLY"`.        | FAIL   | BUG-003   |
| TC-014    | Returned `200 OK` instead of expected `400 Bad Request`; response returned `"status": "CREATE ENTRY SUCCESSFULLY"`.        | FAIL   | BUG-003   |
| TC-015    | Returned `200 OK` and the game with ID `6` updated successfully.                                                           | PASS   | N/A       |
| TC-016    | Returned `200 OK` and the game with ID `6` updated successfully.                                                           | PASS   | N/A       |
| TC-017    | Returned `200 OK` instead of expected `400 Bad Request`; response returned `"status": "UPDATE ITEM SUCCESSFULLY"`.         | FAIL   | BUG-004   |
| TC-018    | Returned `200 OK` instead of expected `400 Bad Request`; response returned `"status": "UPDATE ITEM SUCCESSFULLY"`.         | FAIL   | BUG-004   |
| TC-019    | Returned `200 OK` instead of expected `404 Not Found`; response returned `"status": "UPDATE ITEM SUCCESSFULLY"`.           | FAIL   | BUG-005   |
| TC-020    | Returned `200 OK` instead of expected `404 Not Found`; response returned `"status": "UPDATE ITEM SUCCESSFULLY"`.           | FAIL   | BUG-005   |
| TC-021    | Returned `200 OK` instead of expected `404 Not Found`; response returned `"status": "UPDATE ITEM SUCCESSFULLY"`.           | FAIL   | BUG-005   |
| TC-022    | Returned `200 OK` and the game with ID `6` deleted successfully.                                                           | PASS   | N/A       |
| TC-023    | Returned `200 OK` instead of expected `404 Not Found`; response returned `"status": "DELETE ITEM SUCCESSFULLY"`.           | FAIL   | BUG-006   |
| TC-024    | Returned `200 OK` instead of expected `404 Not Found`; response returned `"status": "DELETE ITEM SUCCESSFULLY"`.           | FAIL   | BUG-006   |
| TC-025    | Returned `200 OK` instead of expected `404 Not Found`; response returned `"status": "DELETE ITEM SUCCESSFULLY"`.           | FAIL   | BUG-006   |
| TC-026    | Returned `200 OK` and all games deleted successfully.                                                                      | PASS   | N/A       |
| TC-027    | Returned `200 OK` and an empty collection returned.                                                                        | PASS   | N/A       |
