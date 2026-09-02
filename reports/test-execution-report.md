# Test Execution Report – SauceDemo

   **Reference:** Test Plan TP-SAUCEDEMO-2026-001
   
   **Project:** SauceDemo-Manual Testing Project
   
   **Build/Version Tested:** Live site as of July 2026
   
   **Tester/Author:** Ananya Biswas
   
   **Test Environment:** Chrome (latest), Linux 

   **Report Date:** 15 July, 2026
   

## Overview

This Test Execution Report summarizes the results of manual functional testing performed on the **SauceDemo (Swag Labs)** web application. Testing covered the core e-commerce workflows defined in the Test Plan, including authentication, product inventory, product details, shopping cart, checkout, order completion, and logout/session management.

## Overall Test Execution Result

| Test Suite                                | Total Test Cases | Passed | Failed |  Pass Rate |  Fail Rate | Overall Status          |
| ----------------------------------------- | ---------------: | -----: | -----: | ---------: | ---------: | ----------------------- |
| Authentication/Login                      |               14 |     10 |      4 |     71.43% |     28.57% | ⚠️ Partially Passed     |
| Product Inventory                         |               11 |      6 |      5 |     54.55% |     45.45% | ⚠️ Partially Passed     |
| Shopping Cart                             |                9 |      4 |      5 |     44.44% |     55.56% | ⚠️ Partially Passed     |
| Product Detail                            |               10 |      8 |      2 |     80.00% |     20.00% | ⚠️ Partially Passed     |
| Checkout: Step One (Customer Information) |               10 |      5 |      5 |     50.00% |     50.00% | ⚠️ Partially Passed     |
| Checkout: Step Two (Overview)             |               13 |     10 |      3 |     76.92% |     23.08% | ⚠️ Partially Passed     |
| Checkout: Complete                        |                9 |      7 |      2 |     77.78% |     22.22% | ⚠️ Partially Passed     |
| Logout/Session Handling                   |                9 |      8 |      1 |     88.89% |     11.11% | ⚠️ Partially Passed     |
| **Overall**                               |           **85** | **58** | **27** | **68.24%** | **31.76%** | **⚠️ Partially Passed** |


## Key Execution Findings

| Area                    | Observation                                                                                                                            |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Authentication          | Core login/logout scenarios passed, with failures identified in input edge cases and direct access behavior.                           |
| Product Inventory       | Core inventory functionality passed, while several special-user scenarios exposed product image, sorting, UI, and interaction defects. |
| Shopping Cart           | Core cart functionality passed, but multiple special-user and empty-cart scenarios failed.                                             |
| Product Detail          | Most product detail functionality passed, with failures identified for invalid product handling and `problem_user` behavior.           |
| Checkout Step One       | Basic checkout functionality passed, while input validation and `problem_user` field interaction issues were identified.               |
| Checkout Step Two       | Most overview functionality passed, with failures related to direct page access, `problem_user`, and `error_user` checkout completion. |
| Checkout Complete       | Order completion and confirmation functionality passed, while direct access and browser Back behavior exposed state-management issues. |
| Logout/Session Handling | Core logout and session protection scenarios passed, while cross-user cart isolation failed.                                           |

## Overall Execution Summary

The SauceDemo test execution achieved a **68.24% pass rate**, with **58 of 85 test cases passing** and **27 failing** across the eight test suites.

The identified failures cover several areas, including:

* User-specific behavior
* Input validation and field handling
* UI interactions and visual defects
* Product-data consistency
* Shopping cart functionality
* Performance behavior
* Checkout state management
* Session and cart data isolation

The **Shopping Cart** suite has the highest failure rate at **55.56%**, followed by **Checkout: Step One** at **50.00%**.

The **Logout/Session Handling** suite achieved the highest pass rate at **88.89%**, while still identifying an important defect related to **cart data isolation between user sessions**.

## Final Assessment

**Overall Status: ⚠️ Partially Passed**

The test execution demonstrates that the core SauceDemo e-commerce workflows are functional, but several defects remain across special-user behavior, validation, cart functionality, checkout state management, and session isolation.

The results provide a clear basis for defect reporting, regression testing, and future automation coverage.
