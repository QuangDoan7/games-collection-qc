# Games Collection API - Quality Control Project

## Project Overview

The Games Collection API - Quality Control Project is designed to evaluate the reliability and correctness of the Games Collection REST API.

The project covers the complete testing lifecycle, including requirements analysis, test planning, test scenario and test case design, manual API testing, defect reporting, confirmation testing, regression testing, and API test automation using Postman and Newman.

## Application Under Test

**Application Repository:** https://github.com/QuangDoan7/games-collection

The application under test (AUT) is the Games Collection RESTful API, which provides endpoints for managing and retrieving information about games in the collection.

The API supports CRUD operations through GET, POST, PUT, and DELETE requests.

## Scope

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

## Testing Approach

The testing approach for the Games Collection API - Quality Control Project includes both manual and automated testing using Postman and Newman.

Manual testing involves designing test scenarios and test cases and executing the test cases to verify the correctness of API responses using Postman.

Automated testing involves creating a Postman collection and executing it through the Newman CLI to support consistent, repeatable, and efficient regression testing.

## Test Results

### Manual Testing Results

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

### Automated Regression Test Results

| Metric            | Result |
| ----------------- | ------ |
| Total Test Cases  | 27     |
| Total Requests    | 38     |
| Total Assertions  | 65     |
| Passed Assertions | 65     |
| Failed Assertions | 0      |
| Execution Status  | PASS   |

## Tools and Technologies

| Category              | Technology / Tool   |
| --------------------- | ------------------- |
| API Architecture      | RESTful API         |
| Backend               | Node.js, Express.js |
| Database              | SQLite              |
| API Testing           | Postman             |
| Automation CLI Runner | Newman              |
| Version Control       | Git                 |
| Repository Hosting    | GitHub              |
| Operating System      | Windows 11 Pro      |
| Test Environment      | Localhost           |

## Repository Structure

```
games-collection-qc/
├── README.md
├───01-Requirements
│       Requirements-Analysis.md
├───02-Test-Plan
│       Test-Plan.md
├───03-Test-Scenarios
│       Test-Scenarios.md
├───04-Test-Cases
│       Test-Cases.md
├───05-Requirements-Traceability-Matrix
│       Requirements-Traceability-Matrix.md
├───06-Test-Execution-Results
│       Test-Execution-Result.md
├───07-Defect-Reports
│       Defect-Reports.md
├───08-Confirmation-Test-Results
│       Confirmation-Test-Results.md
├───09-Regression-Testing
│       Regression-Testing.md
├───10-Test-Summary-Report
│       Test-Summary-Report.md
├───11-Automation
│       Games Collection API Tests.postman_collection.json
└───12-Automation-Test-Report
        Automation-Test-Report.md
```

## Key Defects Identified

| Defect ID | Description                                                                                                                | Status   |
| --------- | -------------------------------------------------------------------------------------------------------------------------- | -------- |
| BUG-001   | GET Game by ID Returns `200 OK` for a Non-existing Game                                                                    | RESOLVED |
| BUG-002   | POST New Game Returns `200 OK` instead of `201 Created`                                                                    | RESOLVED |
| BUG-003   | POST New Game accepts Missing Required Game Name or Invalid Release Year and Returns `200 OK` instead of `400 Bad Request` | RESOLVED |
| BUG-004   | PUT Existing Game Using Invalid Release Year Returns `200 OK` instead of `400 Bad Request`                                 | RESOLVED |
| BUG-005   | PUT Existing Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`                                | RESOLVED |
| BUG-006   | DELETE Game Using Invalid/Non-existing ID Returns `200 OK` instead of `404 Not Found`                                      | RESOLVED |

## How to Run the Automated Tests

### Prerequisites

Before running the automated tests, ensure that:

- The Games Collection backend is running.
- The API is accessible at `http://localhost:3001`.
- Newman is installed and available from the command line.

### Run the Tests

To run the automated tests using Newman, follow these steps:

1. Open a terminal or command prompt.
2. Navigate to the root directory of the repository.
3. Run the following command to execute the automated tests using Newman:

   ```
   newman run ".\11-Automation\Games Collection API Tests.postman_collection.json" --env-var "baseUrl=http://localhost:3001"
   ```

4. Review the test results displayed in the terminal to verify the execution status and any failed assertions.
