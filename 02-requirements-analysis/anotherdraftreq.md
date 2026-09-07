# Requirement Analysis – SauceDemo

## Purpose

The purpose of this requirements analysis is to establish a clear and testable understanding of the expected behavior of the SauceDemo application before test design and execution.

Because SauceDemo does not provide formal requirements, the requirements were reverse-engineered from observed application behavior and user workflows. They define the key functional requirements, business rules, validation rules, navigation behavior, and expected system responses, and serve as the basis for test case design and traceability.

## Application Overview

SauceDemo (Swag Labs) is a sample e-commerce application covering login, product browsing, cart management, checkout, and logout. Predefined users simulate different application behaviors, including `problem_user`, `error_user`, `performance_glitch_user`, and `visual_user`.

Reference: Test Plan [TP-SAUCEDEMO-2026-001](../01-test-plan/test-plan.md)

---

## Authentication / Login

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-AUTH-01 | System shall authenticate users based on username <br> and password, allowing valid predefined users to log in <br> and rejecting  invalid attempts with appropriate error <br>feedback. | Valid credentials → login succeeds<br>Wrong password → rejected with error<br>Blank username → required-field error<br>Unregistered credentials → rejected<br>Locked-out account → login blocked<br>Special-behavior users can log in |
| REQ-AUTH-02 | System shall load the Inventory page within an <br> acceptable response time following a successful login. | Inventory page loads within acceptable time |
| REQ-AUTH-03 | System shall restrict access to authenticated pages <br>unless a valid session exists. | No session → redirected to Login page |

---

## Product Inventory

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-INV-01 | System shall display the Inventory page after login and allow navigation to and from individual product details. | Inventory page loads after login<br>Clicking a product name navigates to its detail page<br>Returning from detail page retains previous sort order |
| REQ-INV-02 | System shall allow products to be sorted by price and name, and correctly reorder them based on the selected option. | Sorting by price low→high reorders correctly<br>Sorting by price high→low reorders correctly<br>Sorting works correctly for `problem_user` |
| REQ-INV-03 | System shall display the correct image for each product on the Inventory page. | All products show valid images, no broken/missing icons<br>Correct image-product association for `problem_user` |
| REQ-INV-04 | System shall present a consistent, correctly aligned layout on the Inventory page. | Layout, spacing, and alignment are correct for `visual_user` |
| REQ-INV-05 | System shall load the Inventory page within an acceptable response time. | Inventory page loads within acceptable time for `performance_glitch_user` |
| REQ-INV-06 | System shall ensure all interactive elements on the Inventory page (buttons, menu links) respond correctly for `error_user`. | All Add to Cart buttons are responsive<br>Burger Menu → About link redirects correctly |

---

## Product Detail

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-DET-01 | System shall navigate to the correct product detail page and display accurate, matching product information. | Clicking a product opens its detail page<br>Product name on detail page matches the selected item<br>Correct product displayed for `problem_user` |
| REQ-DET-02 | System shall display all required product information completely and correctly on the detail page. | All required elements (image, name, description, price, buttons) are visible<br>Product description displays fully, without truncation<br>Product image loads correctly |
| REQ-DET-03 | System shall allow adding and removing products to/from the cart directly from the detail page. | Add to Cart adds product and updates button/badge<br>Remove removes product and updates button/badge |
| REQ-DET-04 | System shall gracefully handle access to invalid or non-existent products and prevent them from proceeding through checkout. | Invalid product URL displays "ITEM NOT FOUND"<br>Invalid products cannot proceed through the checkout flow |

---

## Shopping Cart

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-CART-01 | System shall allow users to add one or more products to the cart, updating the button state and cart badge accordingly. | Single, multiple, and all products can be added with the cart badge updating correctly<br>Product data and image are correct for `problem_user`<br>All products can be added for `error_user` |
| REQ-CART-02 | System shall allow users to remove products from the cart, updating the button state and cart badge accordingly. | Removing a product updates button and badge<br>Removal works correctly for `error_user` |
| REQ-CART-03 | System shall display the Cart page with correct layout, alignment, and positioning of elements. | Cart layout, icon alignment, and Checkout button position are correct for `visual_user` |
| REQ-CART-04 | System shall prevent users from proceeding to checkout when the cart is empty. | Checkout is blocked when cart is empty |

---

## Checkout Step One (Customer Information)

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-CKT1-01 | System shall display the Checkout Step One page with all required customer information fields and navigation controls. | Checkout Step One page loads with correct title<br>All required fields and buttons are displayed |
| REQ-CKT1-02 | System shall validate customer information fields and allow progression only when valid data is provided. | Valid information allows progression to Step Two<br>Empty fields are rejected with a required-field error |
| REQ-CKT1-03 | System shall allow users to cancel out of Checkout Step One and return to the Cart page without losing cart contents. | Cancel returns to Cart page with items unchanged |
| REQ-CKT1-04 | System shall correctly accept and register keyboard input into each customer information field. | All fields accept input correctly for `problem_user`<br>Valid input in all fields allows progression to the next step |
| REQ-CKT1-05 | System shall prevent access to Checkout Step One when the cart is empty. | Direct URL access is blocked when cart is empty |

---

## Checkout Step Two (Overview)

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-CKT2-01 | System shall display the Checkout Overview page only after valid customer information has been submitted, and shall block direct access when the cart is empty. | Overview page loads after valid Step One submission<br>Direct URL access is blocked when cart is empty |
| REQ-CKT2-02 | System shall accurately display all cart items, their details, and quantities on the Overview page. | All cart items are listed with correct details<br>Item details match what was added to cart<br>Item quantity is displayed correctly |
| REQ-CKT2-03 | System shall display dummy payment and shipping information on the Overview page. | Payment Information section is displayed<br>Shipping Information section is displayed |
| REQ-CKT2-04 | System shall correctly calculate and display the item total, tax, and overall total. | Price Total section is displayed<br>Item Total equals the exact sum of item prices |
| REQ-CKT2-05 | System shall allow users to complete or cancel the order from the Overview page. | Finish completes the order and navigates to confirmation<br>Cancel returns to Inventory with cart unchanged<br>Order completion succeeds for `error_user` |

---

## Checkout Complete

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-CKTC-01 | System shall display the Checkout Complete page with the correct title, confirmation message, and navigation elements after order completion. | Page loads with correct title after Finish<br>Confirmation message is displayed<br>Confirmation sub-text is displayed<br>Back Home button is visible |
| REQ-CKTC-02 | System shall allow users to return to the Inventory page after order completion via the Back Home button. | Back Home navigates to Inventory page |
| REQ-CKTC-03 | System shall clear all cart contents once an order is completed. | Cart is empty and badge is hidden after completion<br>Cart remains empty with no previous items on re-check |
| REQ-CKTC-04 | System shall prevent access to the Checkout Complete page, and prevent order resubmission, outside of a valid completed-checkout flow. | Direct URL access without a completed order is blocked<br>Browser Back does not return to a resubmittable completed-order state |

---

## Logout & Session Management

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-SESS-01 | System shall provide a visible and functional logout option that terminates the user's session and returns them to the Login page. | Logout option is visible in the navigation menu<br>Clicking Logout logs the user out and redirects to Login page<br>Login page is displayed correctly after logout |
| REQ-SESS-02 | System shall fully terminate the session on logout and prevent access to any previously authenticated page. | Inventory page is inaccessible via direct URL after logout<br>Browser Back does not restore access to Inventory after logout<br>Checkout page is inaccessible after logout<br>No previously authenticated pages remain accessible after logout |
| REQ-SESS-03 | System shall persist cart contents across a re-login for the same user, and maintain independent cart state per user session. | Cart items persist for the same user after logout/login<br>Cart data is isolated between different user sessions |

---

## Non-Functional Observations

This project's test design used SauceDemo's predefined special users (`problem_user`, `error_user`, `performance_glitch_user`, `visual_user`) to simulate different failure conditions. Because each of these users is exercised through ordinary functional test cases, the line between functional and non-functional testing is naturally blurred here — a login test, for example, is still a functional check, but when run against `performance_glitch_user` it also surfaces a performance-quality observation. Rather than duplicating these as separate non-functional requirements, they are cross-referenced below against the functional requirements that already cover them.

| Category | Related Functional Requirement(s) | Observation |
|---|---|---|
| Performance | REQ-AUTH-02, REQ-INV-05 | Noticeable load-time delay for `performance_glitch_user` |
| Usability / Responsiveness | REQ-INV-06, REQ-CART-01, REQ-CART-02, REQ-CKT2-05 | Unresponsive UI elements (buttons, links) for `error_user` |
| UI / Visual Consistency | REQ-INV-04, REQ-CART-03 | Layout and alignment inconsistencies for `visual_user` |

## Out of Scope

- **Compatibility** — No cross-browser or cross-device testing was performed.
- **Load/Performance testing** — Performance observations were limited to manual, single-user page-load checks.

## Assumptions

- SauceDemo does not provide official requirement documentation; requirements were reverse-engineered from observed application behavior.
- Where behavior was ambiguous or inconsistent, requirements reflect the intended behavior for standard usage, with deviations treated as defects.
- Requirements reflect observations made in July 2026 and may not account for later changes to the live site.
