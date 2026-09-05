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
| Product Inventory                         |               11 |      6 |      5 |     54.55% |     45.45% | ⚠️ Partially Passed     |
| Shopping Cart                             |                9 |      4 |      5 |     44.44% |     55.56% | ⚠️ Partially Passed     |
| Product Detail                            |               10 |      8 |      2 |     80.00% |     20.00% | ⚠️ Partially Passed     |
| Checkout: Step One (Customer Information) |                8 |      5 |      3 |     62.50% |     37.50% | ⚠️ Partially Passed     |
| Checkout: Step Two (Overview)             |               12 |     10 |      2 |     83.33% |     16.67% | ⚠️ Partially Passed     |
| Checkout: Complete                        |                9 |      7 |      2 |     77.78% |     22.22% | ⚠️ Partially Passed     |
| Logout/Session Handling                   |                9 |      8 |      1 |     88.89% |     11.11% | ⚠️ Partially Passed     |
| **Overall**                               |           **79** | **58** | **21** | **73.42%** | **26.58%** | **⚠️ Partially Passed** |

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

The SauceDemo test execution achieved a 73.42% pass rate, with 58 of 79 test cases passing and 21 failing across the eight test suites.

The identified failures cover several areas, including:

* User-specific behavior
* Input and field handling
* UI interactions and visual defects
* Product-data consistency
* Shopping cart functionality
* Performance behavior
* Checkout state management
* Session and cart data isolation

The Shopping Cart suite has the highest failure rate at 55.56%, followed by Product Inventory at 45.45% and Checkout: Step One at 37.50%.

The Authentication/Login suite achieved the highest pass rate at 90.91%, with only one failed test case related to direct access to the Inventory page without authentication.

## Cross-Cutting Observations

Several failures recur across multiple, otherwise unrelated suites, suggesting shared root causes rather than isolated defects:

* **Checkout flow state-validation bypass** – observed at multiple entry points, including checkout initiation with an empty cart and direct access to checkout pages, indicating that the application does not consistently enforce checkout sequence prerequisites.
* **`problem_user` product data/image mismatch** – observed consistently across Product Inventory, Product Detail, Shopping Cart, and Checkout Step Two.

## Defect Summary

Defect logging and severity classification are currently **in progress**. A full breakdown by severity (Critical/High/Medium/Low) will be added once the defect log is finalized; see `/defects` for individual bug reports as they are completed.

## Final Assessment

**Overall Status: ⚠️ Partially Passed**

The test execution demonstrates that the core SauceDemo e-commerce workflows are functional, but several defects remain across special-user behavior, field handling, cart functionality, checkout state management, and session isolation.

The results provide a clear basis for defect reporting, regression testing, and future automation coverage.
