# Test Execution Report – SauceDemo

**Reference:** Test Plan TP-SAUCEDEMO-2026-001

**Project:** SauceDemo-Manual Testing Project

**Build/Version Tested:** Live site as of July 2026

**Tester/Author:** Ananya Biswas

**Test Environment:** Chrome (latest), Linux

**Report Date:** 15 July, 2026

## Overview

This Test Execution Report summarizes the results of manual functional testing performed on the SauceDemo (Swag Labs) web application. Testing covered the core e-commerce workflows defined in the Test Plan, including authentication, product inventory, product details, shopping cart, checkout, order completion, and logout/session management.

## Overall Test Execution Result

| Test Suite                                | Total Test Cases | Passed | Failed |  Pass Rate |  Fail Rate | Overall Status          |
| ----------------------------------------- | ---------------: | -----: | -----: | ---------: | ---------: | ----------------------- |
| Authentication/Login                      |               11 |     10 |      1 |     90.91% |      9.09% | ⚠️ Partially Passed     |
| Product Inventory                         |               12 |      6 |      6 |     50.00% |     50.00% | ⚠️ Partially Passed     |
| Shopping Cart                             |                9 |      4 |      5 |     44.44% |     55.56% | ⚠️ Partially Passed     |
| Product Detail                            |               10 |      8 |      2 |     80.00% |     20.00% | ⚠️ Partially Passed     |
| Checkout: Step One (Customer Information) |                8 |      5 |      3 |     62.50% |     37.50% | ⚠️ Partially Passed     |
| Checkout: Step Two (Overview)             |               12 |     10 |      2 |     83.33% |     16.67% | ⚠️ Partially Passed     |
| Checkout: Complete                        |                9 |      7 |      2 |     77.78% |     22.22% | ⚠️ Partially Passed     |
| Logout/Session Handling                   |                9 |      8 |      1 |     88.89% |     11.11% | ⚠️ Partially Passed     |
| **Overall**                               |           **80** | **58** | **22** | **72.50%** | **27.50%** | **⚠️ Partially Passed** |

## Key Execution Findings

| Area                    | Observation                                                                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Authentication          | Core login scenarios passed, with a failure identified in direct access to the Inventory page without authentication.                  |
| Product Inventory       | Core inventory functionality passed, while several special-user scenarios exposed product image, sorting, UI, and interaction defects. |
| Shopping Cart           | Core cart functionality passed, but multiple special-user and empty-cart scenarios failed.                                             |
| Product Detail          | Most product detail functionality passed, with failures identified for invalid product handling and `problem_user` behavior.           |
| Checkout Step One       | Basic checkout functionality passed, while `problem_user` field interaction and checkout progression issues were identified.           |
| Checkout Step Two       | Most overview functionality passed, with failures related to direct page access, `problem_user`, and `error_user` checkout completion. |
| Checkout Complete       | Order completion and confirmation functionality passed, while direct access and browser Back behavior exposed state-management issues. |
| Logout/Session Handling | Core logout and session protection scenarios passed, while cross-user cart isolation failed.                                           |

## Overall Execution Summary

The SauceDemo test execution achieved a **72.50%** pass rate, with 58 of 80 test cases passing and 22 failing across the eight test suites.

The identified failures cover several areas, including:

* User-specific behavior
* Input and field handling
* UI interactions and visual defects
* Product-data consistency
* Shopping cart functionality
* Performance behavior
* Checkout state management
* Session and cart data isolation

The Shopping Cart suite has the highest failure rate at 55.56%, followed by Product Inventory at 50.00%  and Checkout: Step One at 37.50%.

The Authentication/Login suite achieved the highest pass rate at 90.91%, with only one failed test case related to direct access to the Inventory page without authentication.

## Cross-Cutting Observations

Several failures recur across multiple, otherwise unrelated suites, suggesting shared root causes rather than isolated defects:

* **Checkout flow state-validation bypass** – observed at multiple entry points, including checkout initiation with an empty cart and direct access to checkout pages, indicating that the application does not consistently enforce checkout sequence prerequisites.
* **`problem_user` product data/image mismatch** – observed consistently across Product Inventory, Product Detail, Shopping Cart, and Checkout Step Two.

## Defect Summary

A total of **22 test-case failures** were identified during execution. These failures resulted in **18 unique defects** being reported and documented in `/defects`.

The remaining **4 failed test cases were duplicate manifestations or alternate entry points of defects already covered by existing bug tickets** and were therefore not logged as separate defects. This ensures that each underlying issue is represented by a single defect ticket while maintaining traceability to all affected test cases.

### Severity Distribution

| Severity  | Number of Defects | Percentage |
| --------- | ----------------: | ---------: |
| Critical  |                 1 |      5.56% |
| High      |                 8 |     44.44% |
| Medium    |                 7 |     38.89% |
| Low       |                 2 |     11.11% |
| **Total** |            **18** |   **100%** |

Overall, **9 of the 18 reported defects (50.00%) are classified as Critical or High severity**, indicating that a significant portion of the identified defects has a substantial impact on core functionality, checkout processing, data isolation, or other important user workflows.

See `/05-bug-reports` for the individual bug reports and supporting evidence.

## Final Assessment

**Overall Status: ⚠️ Partially Passed**

The test execution demonstrates that the core SauceDemo e-commerce workflows are functional, but several defects remain across special-user behavior, field handling, cart functionality, checkout state management, and session isolation.

The results provide a clear basis for defect reporting, regression testing, and future automation coverage.
