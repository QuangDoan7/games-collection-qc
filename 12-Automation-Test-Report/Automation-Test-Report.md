# Games Collection - API Automation Test Report

## Automation Information

**API:** RESTful API
**Tool:** Postman
**CLI Runner:** Newman
**Environment:** Localhost
**Base URL:** http://localhost:3001

## Objective

The objective of this automation API test is to verify the functionality and reliability of the Games Collection API by executing a series of automated test cases using Postman and Newman.

## Scope

API Operations Covered:

- GET: Retrieve a specific game by ID or a list of all games.
- POST: Add a new game to the collection.
- PUT: Update an existing game in the collection.
- DELETE: Remove a game or all games from the collection.

## Automation Approach

- The automation tests are implemented using Postman collections, which include test scripts for each API endpoint.
- Assertions check the correctness of API responses, including status codes and the response body content.
- Newman is used as the CLI runner to execute the Postman collections and display the automated test execution results.
- Test data is managed within the Postman collections, allowing for consistent and repeatable test execution.

## Execution Command

```bash

newman run "{path_to_postman_collection}\Games Collection API Tests.postman_collection.json" --env-var "baseUrl=http://localhost:3001"

```

## Automation Results

Total test Cases: 27
Total Requests: 38
Total Assertions: 65
Passed Assertions: 65
Failed Assertions: 0
Execution Status: PASS

## Test Data Management

- Test data is managed within the Postman collection to support consistent and repeatable automated test execution.
- After TC-026, TC-027, and TC-008 verify operations on an empty collection, the initial five-game dataset is restored before continuing with TC-009 and the subsequent test cases.
- At the end of the automation run, the collection is reset again to its initial state so that subsequent regression runs can be executed without manually resetting the database or restarting the backend server.

## Conclusion

The automation tests for the Games Collection API have been successfully executed using Postman and Newman. All test cases passed, indicating that the API is functioning correctly and reliably. The test data management approach ensures consistent and repeatable test execution, maintaining the integrity of the test environment.
