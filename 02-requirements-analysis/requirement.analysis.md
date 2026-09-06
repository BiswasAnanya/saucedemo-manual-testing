# Requirement Analysis – SauceDemo

## Purpose and Approach

The purpose of this requirements analysis is to establish a clear and testable understanding of the expected behavior of the SauceDemo application before test design and execution.

Because SauceDemo does not provide formal business or functional requirements, the requirements were reverse-engineered from the application's observed behavior and user workflows. The analysis identifies the key functional requirements, business rules, validation rules, navigation behavior, and expected system responses across the main e-commerce workflows.

Each identified requirement was analyzed and converted into testable conditions. The resulting requirements were then mapped to test cases to establish traceability between application functionality and QA coverage.

## Application Overview

SauceDemo (Swag Labs) is a sample e-commerce web application used for QA practice. It covers core online shopping workflows — login, product browsing, cart management, checkout, and logout — along with a set of predefined users that simulate different application behaviors (e.g., `problem_user`, `error_user`, `performance_glitch_user`).

Reference: Test Plan [TP-SAUCEDEMO-2026-001](../01-test-plan/test-plan.md)

## Functional Requirements

## Authentication / Login

### REQ-AUTH-01: User Authentication

The system shall authenticate users based on username and password, allowing valid predefined users to log in and rejecting invalid attempts with appropriate error feedback.

**Acceptance Criteria:**
- Valid credentials → login succeeds
- Wrong password → rejected with error
- Blank username → required-field error
- Unregistered credentials → rejected
- Locked-out account → login blocked
- Special-behavior users can log in

### REQ-AUTH-02: Login Performance

The system shall load the Inventory page within an acceptable response time following a successful login.

**Acceptance Criteria:**
- Inventory page loads within acceptable time

### REQ-AUTH-03: Session Protection

The system shall restrict access to authenticated pages unless a valid session exists.

**Acceptance Criteria:**
- No session → redirected to Login page

## Product Inventory

### REQ-INV-01: Inventory Page Display & Navigation

The system shall display the Inventory page after login and allow navigation to and from individual product details.

**Acceptance Criteria:**
- Inventory page loads after login
- Clicking a product name navigates to its detail page
- Returning from detail page retains previous sort order

### REQ-INV-02: Product Sorting

The system shall allow products to be sorted by price and name, and correctly reorder them based on the selected option.

**Acceptance Criteria:**
- Sorting by price low→high reorders correctly
- Sorting by price high→low reorders correctly
- Sorting works correctly for `problem_user`

### REQ-INV-03: Product Image Accuracy

The system shall display the correct image for each product on the Inventory page.

**Acceptance Criteria:**
- All products show valid images, no broken/missing icons
- Correct image-product association for `problem_user`

### REQ-INV-04: UI/Visual Presentation

The system shall present a consistent, correctly aligned layout on the Inventory page.

**Acceptance Criteria:**
- Layout, spacing, and alignment are correct for `visual_user`

### REQ-INV-05: Page Load Performance

The system shall load the Inventory page within an acceptable response time.

**Acceptance Criteria:**
- Inventory page loads within acceptable time for `performance_glitch_user`

### REQ-INV-06: Interactive Element Responsiveness

The system shall ensure all interactive elements on the Inventory page (buttons, menu links) respond correctly for `error_user`.

**Acceptance Criteria:**
- All Add to Cart buttons are responsive
- Burger Menu → About link redirects correctly

## Product Detail

### REQ-DET-01: Product Detail Navigation & Accuracy

The system shall navigate to the correct product detail page and display accurate, matching product information.

**Acceptance Criteria:**
- Clicking a product opens its detail page
- Product name on detail page matches the selected item
- Correct product displayed for `problem_user`

### REQ-DET-02: Product Detail Page Content

The system shall display all required product information completely and correctly on the detail page.

**Acceptance Criteria:**
- All required elements (image, name, description, price, buttons) are visible
- Product description displays fully, without truncation
- Product image loads correctly

### REQ-DET-03: Cart Actions from Detail Page

The system shall allow adding and removing products to/from the cart directly from the detail page.

**Acceptance Criteria:**
- Add to Cart adds product and updates button/badge
- Remove removes product and updates button/badge

### REQ-DET-04: Invalid Product Handling

The system shall gracefully handle access to invalid or non-existent products and prevent them from proceeding through checkout.

**Acceptance Criteria:**
- Invalid product URL displays "ITEM NOT FOUND"
- Invalid products cannot proceed through the checkout flow

## Shopping Cart

### REQ-CART-01: Add Products to Cart

The system shall allow users to add one or more products to the cart, updating the button state and cart badge accordingly.

**Acceptance Criteria:**
- Adding a single product updates button and badge to 1
- Adding multiple products updates badge to 3
- Adding all products updates badge to 6
- Correct product/image added for `problem_user`
- All products can be added for `error_user`

### REQ-CART-02: Remove Products from Cart

The system shall allow users to remove products from the cart, updating the button state and cart badge accordingly.

**Acceptance Criteria:**
- Removing a product updates button and badge
- Removal works correctly for `error_user`

### REQ-CART-03: Cart Page UI

The system shall display the Cart page with correct layout, alignment, and positioning of elements.

**Acceptance Criteria:**
- Cart layout, icon alignment, and Checkout button position are correct for `visual_user`

### REQ-CART-04: Checkout Eligibility

The system shall prevent users from proceeding to checkout when the cart is empty.

**Acceptance Criteria:**
- Checkout is blocked when cart is empty

## Checkout Step One (Customer Information)

### REQ-CKT1-01: Checkout Step One Page & Form Display

The system shall display the Checkout Step One page with all required customer information fields and navigation controls.

**Acceptance Criteria:**
- Checkout Step One page loads with correct title
- All required fields and buttons are displayed

### REQ-CKT1-02: Customer Information Validation

The system shall validate customer information fields and allow progression only when valid data is provided.

**Acceptance Criteria:**
- Valid information allows progression to Step Two
- Empty fields are rejected with a required-field error

### REQ-CKT1-03: Checkout Navigation Controls

The system shall allow users to cancel out of Checkout Step One and return to the Cart page without losing cart contents.

**Acceptance Criteria:**
- Cancel returns to Cart page with items unchanged

### REQ-CKT1-04: Form Field Input Handling

The system shall correctly accept and register keyboard input into each customer information field.

**Acceptance Criteria:**
- All fields accept input correctly for `problem_user`
- Valid input in all fields allows progression to the next step

### REQ-CKT1-05: Checkout Access Restriction

The system shall prevent access to Checkout Step One when the cart is empty.

**Acceptance Criteria:**
- Direct URL access is blocked when cart is empty

## Checkout Step Two (Overview)

### REQ-CKT2-01: Checkout Overview Page Access

The system shall display the Checkout Overview page only after valid customer information has been submitted, and shall block direct access when the cart is empty.

**Acceptance Criteria:**
- Overview page loads after valid Step One submission
- Direct URL access is blocked when cart is empty

### REQ-CKT2-02: Cart Item Accuracy on Overview

The system shall accurately display all cart items, their details, and quantities on the Overview page.

**Acceptance Criteria:**
- All cart items are listed with correct details
- Item details match what was added to cart
- Item quantity is displayed correctly

### REQ-CKT2-03: Payment & Shipping Information Display

The system shall display dummy payment and shipping information on the Overview page.

**Acceptance Criteria:**
- Payment Information section is displayed
- Shipping Information section is displayed

### REQ-CKT2-04: Order Total Calculation

The system shall correctly calculate and display the item total, tax, and overall total.

**Acceptance Criteria:**
- Price Total section is displayed
- Item Total equals the exact sum of item prices

### REQ-CKT2-05: Order Completion & Cancellation

The system shall allow users to complete or cancel the order from the Overview page.

**Acceptance Criteria:**
- Finish completes the order and navigates to confirmation
- Cancel returns to Inventory with cart unchanged
- Order completion succeeds for `error_user`

## Checkout Complete

### REQ-CKTC-01: Checkout Complete Page Display

The system shall display the Checkout Complete page with the correct title, confirmation message, and navigation elements after order completion.

**Acceptance Criteria:**
- Page loads with correct title after Finish
- Confirmation message is displayed
- Confirmation sub-text is displayed
- Back Home button is visible

### REQ-CKTC-02: Post-Order Navigation

The system shall allow users to return to the Inventory page after order completion via the Back Home button.

**Acceptance Criteria:**
- Back Home navigates to Inventory page

### REQ-CKTC-03: Cart Clearing After Order Completion

The system shall clear all cart contents once an order is completed.

**Acceptance Criteria:**
- Cart is empty and badge is hidden after completion
- Cart remains empty with no previous items on re-check

### REQ-CKTC-04: Checkout Completion Access Control

The system shall prevent access to the Checkout Complete page, and prevent order resubmission, outside of a valid completed-checkout flow.

**Acceptance Criteria:**
- Direct URL access without a completed order is blocked
- Browser Back does not return to a resubmittable completed-order state

## Logout & Session Management

### REQ-SESS-01: Logout Functionality

The system shall provide a visible and functional logout option that terminates the user's session and returns them to the Login page.

**Acceptance Criteria:**
- Logout option is visible in the navigation menu
- Clicking Logout logs the user out and redirects to Login page
- Login page is displayed correctly after logout

### REQ-SESS-02: Session Termination & Page Protection

The system shall fully terminate the session on logout and prevent access to any previously authenticated page.

**Acceptance Criteria:**
- Inventory page is inaccessible via direct URL after logout
- Browser Back does not restore access to Inventory after logout
- Checkout page is inaccessible after logout
- No previously authenticated pages remain accessible after logout

### REQ-SESS-03: Cart Persistence & Isolation

The system shall persist cart contents across a re-login for the same user, and maintain independent cart state per user session.

**Acceptance Criteria:**
- Cart items persist for the same user after logout/login
- Cart data is isolated between different user sessions

## Non-Functional Requirements

This project's test design used SauceDemo's predefined special users (`problem_user`, `error_user`, `performance_glitch_user`, `visual_user`) to simulate different failure conditions. Because each of these users is exercised through ordinary functional test cases, the line between functional and non-functional testing is naturally blurred here — a login test, for example, is still a functional check, but when run against `performance_glitch_user` it also surfaces a performance-quality observation. Rather than duplicating these as separate non-functional requirements, they are cross-referenced below against the functional requirements that already cover them.

| Category | Related Functional Requirement(s) | Observation |
|---|---|---|
| Performance | REQ-AUTH-02, REQ-INV-05 | Noticeable load-time delay for `performance_glitch_user` |
| Usability / Responsiveness | REQ-INV-06, REQ-CART-01, REQ-CART-02, REQ-CKT2-05 | Unresponsive UI elements (buttons, links) for `error_user` |
| UI / Visual Consistency | REQ-INV-04, REQ-CART-03 | Layout and alignment inconsistencies for `visual_user` |

### Out of Scope

The following non-functional areas were not evaluated as part of this project:

* **Compatibility** — testing was limited to Chrome on a single OS; no cross-browser or cross-device testing was performed.
* **Load/Performance testing** — no dedicated load-testing tools were used; performance observations above are limited to manual, single-user page-load observation.

## Assumptions

* SauceDemo does not provide official requirement documentation; all requirements in this document were reverse-engineered from observed application behavior rather than derived from a formal specification.
* Where application behavior was ambiguous or inconsistent (e.g., special-user quirks), the requirement was written to reflect the intended/expected behavior for standard usage, with deviations treated as defects rather than alternate valid requirements.
* Requirements reflect the application's behavior as observed in July 2026 and may not account for later changes to the live site.
