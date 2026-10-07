# Games Collection - Test Plan

## 1. Introduction

This test plan defines the testing activities for the Games Collection application.

## 2. Objectives

- Verify RESTful API functionality.
- Verify CRUD operations.
- Identify any defects.
- Verify application behavior against requirements.

## 3. Scope

### 3.1 In Scope

- RESTful API
- CRUD operations
- Game data handling
- Error handling

### 3.2 Out of Scope

- Performance testing
- Security penetration testing
- Load testing
- Cross-platform compatibility

## 4. Test Items

GET item endpoint
GET collection endpoint
POST collection endpoint
PUT item endpoint
DELETE item endpoint
DELETE collection endpoint

## 5. Test Approach

### Testing Types

- Manual Testing
- Functional Testing
- API Testing
- Positive Testing
- Negative Testing
- Regression Testing

### Test Design Techniques

- Equivalence Partitioning
- Error Guessing

## 6. Test Environment

Operating System: Windows 11
Backend: Node.js / Express
Database: SQLite
API Architecture: REST

## 7. Test Tools

Postman: RESTful API testing
VS Code: Documentation
GitHub: Version control - defect tracking

## 8. Entry Criteria

- Application is available for testing.
- RESTful API server can be started successfully.
- Test database is available.
- Requirements have been reviewed.

## 9. Exit Criteria

- All planned test cases have been executed.
- All critical defects have been resolved.
- Failed tests have been reviewed.
- Retesting has been completed where required.
- Regression testing has been completed.
- Test summary report has been prepared.

## 10. Test Deliverables

Requirements Analysis
Test Plan
Test Scenarios
Test Cases
Requirements Traceability Matrix
Test Execution Results
Defect Reports
Regression Test Results
Test Summary Report

## 11. Risks and Mitigations

| Risk                                 | Impact                               | Mitigation                                      |
| ------------------------------------ | ------------------------------------ | ----------------------------------------------- |
| Requirements are incomplete          | Expected behavior may be unclear     | Document unclear requirements as open questions |
| Test data is modified during testing | Test results may become inconsistent | Reset test database before execution            |

## 12. Roles and Responsibilities

As this is an individual project, the roles of Product Owner, Developer, and QC Tester are performed by Thanh.

Responsibilities:

- Test planning
- Test design
- Test execution
- Defect reporting
- Regression testing

## 13. Schedule

| Activity                          | Estimated Duration |
| --------------------------------- | ------------------ |
| Requirements Analysis             | Completed          |
| Test Planning                     | 1 day              |
| Test Scenario & Test Case Design  | 1-2 days           |
| Test Execution & Defect Reporting | 1-2 days           |
| Defect Fixing & Retesting         | As needed          |
| Regression Testing                | 1 day              |
| Test Closure & Summary Report     | 1 day              |
