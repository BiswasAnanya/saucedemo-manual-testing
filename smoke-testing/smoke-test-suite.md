# Smoke Test Suite – SauceDemo

## Overview

This Smoke Test Suite contains a prioritized subset of SauceDemo functional test cases selected to validate the application's most critical business workflows.

The smoke suite focuses on the primary customer journey:

**Login → Browse Products → Add to Cart → Checkout → Order Confirmation**

It also includes essential logout functionality. These scenarios provide a quick assessment of whether the application is stable enough for further functional or regression testing.

The same smoke test cases will be used for both **manual testing** and **Playwright + TypeScript automation**, providing traceability between the manual QA phase and subsequent automation phase. The original manual test case IDs are referenced below to maintain traceability between the complete test suite and the prioritized smoke coverage.

## Smoke Test Suite

| Smoke Test ID | Source Test Case | Title                                              | Preconditions                                           | Test Data                      | Expected Result                                                                                  | Priority |
| ------------- | ---------------- | -------------------------------------------------- | ------------------------------------------------------- | ------------------------------ | ------------------------------------------------------------------------------------------------ | -------- |
| SMK-001       | TC-001           | Verify login with valid credentials                | Browser is open on SauceDemo Login page                 | `standard_user/secret_sauce`   | User successfully logs in and lands on the Inventory/Products page.                              | Critical |
| SMK-002       | TC-101           | Verify Inventory page loads after login            | User has successfully logged in                         | `standard_user`                | Inventory page loads successfully and Products are displayed.                                    | Critical |
| SMK-003       | TC-301           | Verify a product can be added to cart              | User is logged in and cart is empty                     | `standard_user`                | Selected product is added, button changes to **Remove**, and cart badge displays `1`.            | Critical |
| SMK-004       | TC-302           | Verify multiple products can be added to cart      | User is logged in, on Inventory page, and cart is empty | `standard_user`                | Multiple selected products are added successfully and the cart badge reflects the correct count. | Critical |
| SMK-005       | TC-401           | Verify Checkout Step One is accessible             | User is logged in and has at least one product in cart  | `standard_user`                | Clicking **Checkout** opens the **Checkout: Your Information** page.                             | Critical |
| SMK-006       | TC-403           | Verify user can proceed from Checkout Step One     | User is on Checkout Step One with products in cart      | Valid customer information     | Valid customer information is accepted and the user proceeds to Checkout Overview.               | Critical |
| SMK-007       | TC-501           | Verify Checkout Overview loads correctly           | Valid customer information has been submitted           | Valid customer information     | Checkout Overview loads successfully and displays the order information.                         | Critical |
| SMK-008       | TC-510           | Verify order can be completed                      | User is on Checkout Overview with a valid cart          | Valid checkout data            | Clicking **Finish** completes the order and displays the order confirmation page.                | Critical |
| SMK-009       | TC-606           | Verify cart is emptied after order completion      | User has successfully completed an order                | N/A                            | After returning Home, the cart is empty and the cart badge is no longer displayed.               | High     |
| SMK-010       | TC-702           | Verify user can successfully log out               | User is logged in and on Inventory page                 | `standard_user/secret_sauce`   | User is logged out successfully and redirected to the Login page.                                | Critical |

## Smoke Coverage

The **10 smoke tests** provide coverage of the application's most important functional areas:

* **Authentication** – Valid login and logout
* **Product Inventory** – Inventory loading and product sorting
* **Shopping Cart** – Adding single and multiple products
* **Checkout** – Customer information and Overview navigation
* **Order Completion** – Completing an order successfully
* **Post-Order State** – Cart clearance after order completion
* **Session Management** – Successful logout



 ## Entry Criteria
   - Application is deployed and accessible

 ## Exit Criteria
   - All 11 smoke tests pass → proceed with full regression suite
   - Any Critical-priority failure → halt further testing, report immediately

 ## Out of Scope for Smoke Testing

   - Negative/invalid input scenarios
   - Special-user behavior (problem_user, error_user, etc.)
   - UI/visual validation
   - Edge cases and boundary testing

## Automation Usage

These smoke tests will serve as the initial automation scope for the **Playwright + TypeScript** test suite.

Each `SMK-XXX` test will be mapped to an automated test case, allowing the same critical functional coverage to be executed repeatedly as a fast regression check after application changes or deployments.

## Traceability

| Smoke Test ID | Source Test Case |
| ------------- | ---------------- |
| SMK-001       | TC-001           |
| SMK-002       | TC-101           |
| SMK-003       | TC-301           |
| SMK-004       | TC-302           |
| SMK-005       | TC-401           |
| SMK-006       | TC-403           |
| SMK-007       | TC-501           |
| SMK-008       | TC-510           |
| SMK-008       | TC-606           |
| SMK-010       | TC-702           |


