# Test Execution Report – SauceDemo

**Reference:** [Test Plan TP-SAUCEDEMO-2026-001](../01-test-plan/test-plan.md) | [RTM](../07-requirement-traceability/requirements-traceability-matrix.md) | [Defect Reports](../05-bug-reports)

**Project:** SauceDemo-Manual Testing Project

**Build/Version Tested:** Live site as of August 2026

**Test Environment:** Chrome (latest), Linux

**Tester/Author:** Ananya Biswas

**Report Date:** 30 August, 2026

## Overview

This Test Execution Report summarizes the results of manual functional testing performed on the [SauceDemo](https://www.saucedemo.com/) (Swag Labs) web application. Testing covered the core e-commerce workflows defined in the Test Plan, including authentication, product inventory, product details, shopping cart, checkout, order completion, and logout/session management.

## Overall Test Execution Result

| Test Suite                                                                                            | Total Test Cases | Passed | Failed |  Pass Rate |  Fail Rate | Overall Status          |
| ------------------------------------------------------------------------------------------------------| ---------------: | -----: | -----: | ---------: | ---------: | ----------------------- |
| [Authentication/Login](../03-test-suites/ts00-authentication-login.md)                                |               11 |     10 |      1 |     90.91% |      9.09% | ⚠️ Partially Passed     |
| [Product Inventory](../03-test-suites/ts01-product-inventory.md)                                      |               12 |      6 |      6 |     50.00% |     50.00% | ⚠️ Partially Passed     |
| [Product Detail](../03-test-suites/ts02-product-detail.md)                                            |               10 |      8 |      2 |     80.00% |     20.00% | ⚠️ Partially Passed     |
| [Shopping Cart](../03-test-suites/ts03-shopping-cart.md)                                              |                9 |      4 |      5 |     44.44% |     55.56% | ⚠️ Partially Passed     |
| [Checkout: Step One (Customer Information)](../03-test-suites/ts04-checkout-stepone-customerinfo.md)  |                8 |      5 |      3 |     62.50% |     37.50% | ⚠️ Partially Passed     |
| [Checkout: Step Two (Overview)](../03-test-suites/ts05-checkout-steptwo-overview.md)                  |               12 |     10 |      2 |     83.33% |     16.67% | ⚠️ Partially Passed     |
| [Checkout: Complete](../03-test-suites/ts06-checkout-stepthree-complete.md)                           |                9 |      7 |      2 |     77.78% |     22.22% | ⚠️ Partially Passed     |
| [Logout/Session Handling](../03-test-suites/ts07-logout-sessionhandling.md)                           |                9 |      8 |      1 |     88.89% |     11.11% | ⚠️ Partially Passed     |
| **Overall**                                                                                           |           **80** | **58** | **22** | **72.50%** | **27.50%** | **⚠️ Partially Passed** |



## Key Execution Findings

| Area                    | Observation                                                                                                                             |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------|
| Authentication/Login    | Core login scenarios passed, with a failure identified in direct access to the Inventory page without authentication.                   |
| Product Inventory       | Core inventory functionality passed, while several special-user scenarios exposed product image, sorting, UI, and interaction defects.  |
| Product Detail          | Most product detail functionality passed, with failures identified for invalid product handling and `problem_user` behavior.            |
| Shopping Cart           | Core cart functionality passed, but multiple special-user and empty-cart scenarios failed.                                              |
| Checkout: Step One      | Basic checkout functionality passed, while `problem_user` field interaction and checkout progression issues were identified.            |
| Checkout: Step Two      | Most overview functionality passed, with failures related to direct page access and error_user checkout completion.                     |
| Checkout: Complete      | Order completion and confirmation functionality passed, while direct access and browser Back behavior exposed state-management issues.  |
| Logout/Session Handling | Core logout and session protection scenarios passed, while cross-user cart isolation failed.                                            |
          
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

The [Shopping Cart](../03-test-suites/ts03-shopping-cart.md) suite has the highest failure rate at 55.56%, followed by [Product Inventory](../03-test-suites/ts01-product-inventory.md) at 50.00%  and [Checkout: Step One (Customer Information)](../03-test-suites/ts04-checkout-stepone-customerinfo.md) at 37.50%.

The [Authentication/Login](../03-test-suites/ts00-authentication-login.md) suite achieved the highest pass rate at 90.91%, with only one failed test case related to direct access to the Inventory page without authentication.

## Cross-Cutting Observations

Several failures recur across multiple suites or share a common root cause, indicating related behavioral patterns rather than isolated test-case failures:

- **Checkout flow state-validation bypass** – observed at multiple entry points, including checkout initiation with an empty cart and direct access to Checkout Step One, Step Two, and Complete pages, indicating that the application does not consistently enforce checkout sequence prerequisites (BUG-010, BUG-013, BUG-015).
- **Cross-user cart data isolation failure** – cart contents persist across different user sessions instead of resetting per user, exposing one user's cart data to another (BUG-017). This is the most significant defect identified during execution.
- **`problem_user` product data/image mismatch** – observed consistently across Product Inventory, Product Detail, and Shopping Cart (BUG-002, BUG-007).
- **Checkout Step One field-level defect and downstream impact** – an unresponsive Last Name field prevents `problem_user` from completing customer information, which in turn blocks checkout progression entirely (BUG-011, BUG-012).
- **Post-order state management** – browser Back navigation after order completion restores a stale, resubmittable order state, distinct from the access-control issues above (BUG-016).

## Defect Summary

A total of 22 test-case failures were identified during execution. These failures resulted in 18 unique defects being reported and documented in [Defect Reports](../05-bug-reports).

The remaining 4 failed test cases were duplicate manifestations or alternate entry points of existing defects and were therefore not logged as separate defects. This ensures that each underlying issue is represented by a single defect ticket while maintaining traceability to all affected test cases. See the [RTM](../07-requirement-traceability/requirements-traceability-matrix.md) for the full requirement-to-test-case-to-defect mapping.

### Severity Distribution

| Severity | Number of Defects | Percentage |
|---|---|---|
| Critical | 2 | 11.11% |
| High | 11 | 61.11% |
| Medium | 2 | 11.11% |
| Low | 3 | 16.67% |
| **Total** | **18** | **100%** |

Overall, 13 of the 18 reported defects (72.22%) are classified as Critical or High severity, indicating that a significant majority of the identified defects have a substantial impact on core functionality, checkout processing, data isolation, or other important user workflows.

See [Defect Reports](../05-bug-reports) for the individual bug reports and supporting evidence.

## Final Assessment

**Overall Status: ⚠️ Partially Passed**

The test execution demonstrates that the primary SauceDemo e-commerce workflows are generally functional, but several defects remain across special-user behavior, field handling, cart functionality, checkout state management, and session isolation.

The results provide a clear basis for defect reporting, regression testing, and future automation coverage.
