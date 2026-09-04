# Test Plan

**Test Plan Identifier:** TP-SAUCEDEMO-2026-001

**Project:** SauceDemo-Manual Testing Project

**Build/Version Tested:** Live site as of July 2026

**Test Environment:** Chrome (latest), Linux

**Document Version:** 1.0

**Author:** Ananya Biswas

**Date:** July 2026


## 1. Introduction

This test plan defines the scope, approach, test data, and deliverables for testing the **SauceDemo** web application.
SauceDemo is a sample e-commerce application designed for QA practice. The application covers key e-commerce workflows including authentication, product browsing, shopping cart management, and checkout.

**System Under Test (SUT):** [SauceDemo](https://www.saucedemo.com/)


## 2. Objective

The objectives of this testing project are to:

* Validate core e-commerce workflows and user journeys.
* Verify positive, negative, edge-case, UI/visual, performance, and session-management scenarios.
* Identify and document application defects and user-specific issues.
* Build a structured manual test suite that can be mapped to automated tests.
* Analyze identified defects for common patterns or root causes across features, rather than treating each as an isolated finding.
* Demonstrate an end-to-end QA workflow from planning through execution and defect reporting.

## 3. Test Approach/Strategy

Testing will follow a **risk-based functional testing approach**.

Testing will cover fundamental positive scenarios as well as negative, edge-case, user-specific, UI/visual, performance, and session-management scenarios.
Testing will also include state-transition scenarios (e.g., verifying application behavior across sequential actions such as cart modification, 
checkout progression, and session changes) to validate business-rule enforcement beyond isolated actions.

`standard_user` is used as the baseline for expected behavior, while the remaining predefined users are used to validate specific application conditions.


## 4. Scope 

### In Scope

* Login & authentication
* Product inventory, sorting & product details
* Shopping cart
* Checkout & order completion
* Logout & session handling
* UI/visual validation
* User-specific behavior

### Out of Scope

* Backend/database validation
* Payment gateway integration
* Performance/load testing
* Security/penetration testing


## 5. Test Coverage

Testing will cover the following functional and non-functional areas:

| Area                        | Coverage                                       |
| --------------------------- | ---------------------------------------------- |
| Authentication              | Positive, negative, validation, locked account |
| Product Inventory           | Listing, sorting, details, images, UI          |
| Shopping Cart               | Add, remove, badge count, persistence          |
| Checkout                    | Form validation, overview, pricing, completion |
| Session Management          | Logout, direct access, navigation              |
| User-Specific Behavior      | Functional, performance, error, visual         |
| UI/Visual                   | Layout, images, consistency                    |
| Edge Cases                  | Boundary and unexpected user interactions      |
| Cross-User Session Behavior | Cart isolation, session termination, data leakage between users |

## 6. Test Entry and Exit Criteria

### 6.1 Entry Criteria

- Test Plan has been reviewed and finalized.
- Manual test cases have been written and reviewed.
- SauceDemo application (https://www.saucedemo.com) is accessible and stable.
- Predefined test user credentials (standard_user, locked_out_user, problem_user, performance_glitch_user, error_user, visual_user) are available and working.
- Test environment (browser, OS) is set up and confirmed.

### 6.2 Exit Criteria

- All planned test cases have been executed.
- All identified defects have been logged with appropriate severity/priority.
- No open defects blocking the critical path (Login → Browse → Add to Cart → Checkout → Order Confirmation).
- Test Execution Report and Test Summary have been completed.
- Smoke suite passes successfully on the final build/version tested.


## 7. Test Data

The System under Test (SUT) provides predefined users with different behaviors. These users will be used to validate both baseline functionality and user-specific conditions.

| User                      | Purpose                            |
| ------------------------- | ---------------------------------- |
| `standard_user`           | Baseline functional testing        |
| `locked_out_user`         | Authentication restriction testing |
| `problem_user`            | Functional and data defect testing |
| `performance_glitch_user` | Performance-related behavior       |
| `error_user`              | Error and interaction behavior     |
| `visual_user`             | Visual and UI testing              |

The predefined SauceDemo credentials/data will be used for testing rather than creating custom application data.


## 8. Test Pass/Fail Criteria

- A test case is **Passed** when,  actual result matches the expected result for the test case.
- A test case is **Failed** when, actual result deviates from the expected result, or a defect blocks core functionality (e.g., login, cart, checkout).

## 9. Defect Severity and Priority

### 9.1 Severity

| Severity | Definition |
|---|---|
| Critical | Blocks critical application functionality or causes major application failure. |
| High | Breaks major functionality but the application remains partially usable. |
| Medium | Causes incorrect behavior or a significant usability/performance issue, but a workaround exists. |
| Low | Minor functional, UI, or cosmetic issue with limited impact. |

### 9.2 Priority

| Priority | Definition |
|---|---|
| P1 | Requires immediate attention; blocks critical functionality or has major user impact. |
| P2 | Should be addressed soon; affects important functionality or user experience. |
| P3 | Can be addressed during normal development work. |
| P4 | Low urgency; can be deferred until higher-priority defects are resolved. |

## 10. Smoke Test Criteria

The smoke suite focuses on critical functionality required for the primary customer journey:

**Login → Browse Products → Add to Cart → Checkout → Order Confirmation**

The smoke suite will therefore prioritize verification of this critical path.
Smoke testing will be used to determine whether the application is sufficiently stable for further testing after a build or deployment.

## 11. Deliverables

Deliverables that are planned for this project are in the following:

* Test Plan
* Requirements Traceability Matrix (RTM)
* Test suites containing Manual Test Cases
* Smoke Test Suite
* Test Execution Report
* Defect Log / Bug Reports
* Test Summary

**N. B:** The automation deliverables will be added as the project progresses.


## 12. Notes

To keep this portfolio project focused and practical, the following formal test-plan portions are intentionally excluded from the current version:

* Detailed test types
* Test schedule
* Test Scenarios
* Risk assumptions
* Approval
  
These sections may be added later if required as the project evolves.

