# Requirement Analysis – SauceDemo

## 1. Purpose and Approach

The purpose of this requirements analysis is to establish a clear and testable understanding of the expected behavior of the SauceDemo application before test design and execution.

Because SauceDemo does not provide formal business or functional requirements, the requirements were reverse-engineered from the application's observed behavior and user workflows. The analysis identifies the key functional requirements, business rules, validation rules, navigation behavior, and expected system responses across the main e-commerce workflows. 

Each identified requirement was analyzed and converted into testable conditions. The resulting requirements were then mapped to test cases to establish traceability between application functionality and QA coverage.

## 2. Application Overview

SauceDemo (Swag Labs) is a sample e-commerce web application used for QA practice. It covers core online shopping workflows — login, product browsing, cart management, checkout, and logout — along with a set of predefined users that simulate different application behaviors (e.g., `problem_user`, `error_user`, `performance_glitch_user`).

Reference: Test Plan [TP-SAUCEDEMO-2026-001](../01-test-plan/test-plan.md)


## 4. Functional Requirements

# Requirement Analysis – Authentication/Login

## REQ-AUTH-01: User Authentication

**Description:** The system shall authenticate users based on username and password, allowing valid predefined users to log in and rejecting invalid attempts with appropriate error feedback.

**Acceptance Criteria:**
- AC-1: Valid credentials → login succeeds (TC-001)
- AC-2: Wrong password → rejected with error (TC-002)
- AC-3: Blank username → required-field error (TC-003, TC-005)
- AC-4: Unregistered credentials → rejected (TC-004)
- AC-5: Locked-out account → login blocked (TC-006)
- AC-6: Special-behavior users can log in (TC-007, TC-009, TC-010)

---

## REQ-AUTH-02: Login Performance

**Description:** The system shall load the Inventory page within an acceptable response time following a successful login.

**Acceptance Criteria:**
- AC-1: Inventory page loads within acceptable time (TC-008)

---

## REQ-AUTH-03: Session Protection

**Description:** The system shall restrict access to authenticated pages unless a valid session exists.

**Acceptance Criteria:**
- AC-1: No session → redirected to Login page (TC-011)

# Requirement Analysis – Product Inventory

## REQ-INV-01: Inventory Page Display & Navigation

**Description:** The system shall display the Inventory page after login and allow navigation to and from individual product details.

**Acceptance Criteria:**
- AC-1: Inventory page loads after login (TC-101)
- AC-2: Clicking a product name navigates to its detail page (TC-105)
- AC-3: Returning from detail page retains previous sort order (TC-106)

---

## REQ-INV-02: Product Sorting

**Description:** The system shall allow products to be sorted by price and name, and correctly reorder them based on the selected option.

**Acceptance Criteria:**
- AC-1: Sorting by price low→high reorders correctly (TC-102)
- AC-2: Sorting by price high→low reorders correctly (TC-103)
- AC-3: Sorting works correctly for `problem_user` (TC-108)

---

## REQ-INV-03: Product Image Accuracy

**Description:** The system shall display the correct image for each product on the Inventory page.

**Acceptance Criteria:**
- AC-1: All products show valid images, no broken/missing icons (TC-104)
- AC-2: Correct image-product association for `problem_user` (TC-107)

---

## REQ-INV-04: UI/Visual Presentation

**Description:** The system shall present a consistent, correctly aligned layout on the Inventory page.

**Acceptance Criteria:**
- AC-1: Layout, spacing, and alignment are correct for `visual_user` (TC-109)

---

## REQ-INV-05: Page Load Performance

**Description:** The system shall load the Inventory page within an acceptable response time.

**Acceptance Criteria:**
- AC-1: Inventory page loads within acceptable time for `performance_glitch_user` (TC-110)

---

## REQ-INV-06: Interactive Element Responsiveness

**Description:** The system shall ensure all interactive elements on the Inventory page (buttons, menu links) respond correctly for `error_user`.

**Acceptance Criteria:**
- AC-1: All Add to Cart buttons are responsive (TC-111)
- AC-2: Burger Menu → About link redirects correctly (TC-112)

# Requirement Analysis – Product Detail

## REQ-DET-01: Product Detail Navigation & Accuracy

**Description:** The system shall navigate to the correct product detail page and display accurate, matching product information.

**Acceptance Criteria:**
- AC-1: Clicking a product opens its detail page (TC-201)
- AC-2: Product name on detail page matches the selected item (TC-203)
- AC-3: Correct product displayed for `problem_user` (TC-210)

---

## REQ-DET-02: Product Detail Page Content

**Description:** The system shall display all required product information completely and correctly on the detail page.

**Acceptance Criteria:**
- AC-1: All required elements (image, name, description, price, buttons) are visible (TC-202)
- AC-2: Product description displays fully, without truncation (TC-204)
- AC-3: Product image loads correctly (TC-205)

---

## REQ-DET-03: Cart Actions from Detail Page

**Description:** The system shall allow adding and removing products to/from the cart directly from the detail page.

**Acceptance Criteria:**
- AC-1: Add to Cart adds product and updates button/badge (TC-206)
- AC-2: Remove removes product and updates button/badge (TC-207)

---

## REQ-DET-04: Invalid Product Handling

**Description:** The system shall gracefully handle access to invalid or non-existent products and prevent them from proceeding through checkout.

**Acceptance Criteria:**
- AC-1: Invalid product URL displays "ITEM NOT FOUND" (TC-208)
- AC-2: Invalid products cannot proceed through the checkout flow (TC-209)

# Requirement Analysis – Shopping Cart

## REQ-CART-01: Add Products to Cart

**Description:** The system shall allow users to add one or more products to the cart, updating the button state and cart badge accordingly.

**Acceptance Criteria:**
- AC-1: Adding a single product updates button and badge to 1 (TC-301)
- AC-2: Adding multiple products updates badge to 3 (TC-302)
- AC-3: Adding all products updates badge to 6 (TC-304)
- AC-4: Correct product/image added for `problem_user` (TC-305)
- AC-5: All products can be added for `error_user` (TC-306)

---

## REQ-CART-02: Remove Products from Cart

**Description:** The system shall allow users to remove products from the cart, updating the button state and cart badge accordingly.

**Acceptance Criteria:**
- AC-1: Removing a product updates button and badge (TC-303)
- AC-2: Removal works correctly for `error_user` (TC-307)

---

## REQ-CART-03: Cart Page UI

**Description:** The system shall display the Cart page with correct layout, alignment, and positioning of elements.

**Acceptance Criteria:**
- AC-1: Cart layout, icon alignment, and Checkout button position are correct for `visual_user` (TC-308)

---

## REQ-CART-04: Checkout Eligibility

**Description:** The system shall prevent users from proceeding to checkout when the cart is empty.

**Acceptance Criteria:**
- AC-1: Checkout is blocked when cart is empty (TC-309)

  # Requirement Analysis – Checkout Step One (Customer Information)

## REQ-CKT1-01: Checkout Step One Page & Form Display

**Description:** The system shall display the Checkout Step One page with all required customer information fields and navigation controls.

**Acceptance Criteria:**
- AC-1: Checkout Step One page loads with correct title (TC-401)
- AC-2: All required fields and buttons are displayed (TC-402)

---

## REQ-CKT1-02: Customer Information Validation

**Description:** The system shall validate customer information fields and allow progression only when valid data is provided.

**Acceptance Criteria:**
- AC-1: Valid information allows progression to Step Two (TC-403)
- AC-2: Empty fields are rejected with a required-field error (TC-404)

---

## REQ-CKT1-03: Checkout Navigation Controls

**Description:** The system shall allow users to cancel out of Checkout Step One and return to the Cart page without losing cart contents.

**Acceptance Criteria:**
- AC-1: Cancel returns to Cart page with items unchanged (TC-405)

---

## REQ-CKT1-04: Form Field Input Handling

**Description:** The system shall correctly accept and register keyboard input into each customer information field.

**Acceptance Criteria:**
- AC-1: All fields accept input correctly for `problem_user` (TC-406)
- AC-2: Valid input in all fields allows progression to the next step (TC-407)

---

## REQ-CKT1-05: Checkout Access Restriction

**Description:** The system shall prevent access to Checkout Step One when the cart is empty.

**Acceptance Criteria:**
- AC-1: Direct URL access is blocked when cart is empty (TC-408)


# Requirement Analysis – Checkout Step Two (Overview)

## REQ-CKT2-01: Checkout Overview Page Access

**Description:** The system shall display the Checkout Overview page only after valid customer information has been submitted, and shall block direct access when the cart is empty.

**Acceptance Criteria:**
- AC-1: Overview page loads after valid Step One submission (TC-501)
- AC-2: Direct URL access is blocked when cart is empty (TC-502)

---

## REQ-CKT2-02: Cart Item Accuracy on Overview

**Description:** The system shall accurately display all cart items, their details, and quantities on the Overview page.

**Acceptance Criteria:**
- AC-1: All cart items are listed with correct details (TC-503)
- AC-2: Item details match what was added to cart (TC-504)
- AC-3: Item quantity is displayed correctly (TC-505)

---

## REQ-CKT2-03: Payment & Shipping Information Display

**Description:** The system shall display dummy payment and shipping information on the Overview page.

**Acceptance Criteria:**
- AC-1: Payment Information section is displayed (TC-506)
- AC-2: Shipping Information section is displayed (TC-507)

---

## REQ-CKT2-04: Order Total Calculation

**Description:** The system shall correctly calculate and display the item total, tax, and overall total.

**Acceptance Criteria:**
- AC-1: Price Total section is displayed (TC-508)
- AC-2: Item Total equals the exact sum of item prices (TC-509)

---

## REQ-CKT2-05: Order Completion & Cancellation

**Description:** The system shall allow users to complete or cancel the order from the Overview page.

**Acceptance Criteria:**
- AC-1: Finish completes the order and navigates to confirmation (TC-510)
- AC-2: Cancel returns to Inventory with cart unchanged (TC-511)
- AC-3: Order completion succeeds for `error_user` (TC-512)

# Requirement Analysis – Checkout Complete

## REQ-CKTC-01: Checkout Complete Page Display

**Description:** The system shall display the Checkout Complete page with the correct title, confirmation message, and navigation elements after order completion.

**Acceptance Criteria:**
- AC-1: Page loads with correct title after Finish (TC-601)
- AC-2: Confirmation message is displayed (TC-602)
- AC-3: Confirmation sub-text is displayed (TC-603)
- AC-4: Back Home button is visible (TC-604)

---

## REQ-CKTC-02: Post-Order Navigation

**Description:** The system shall allow users to return to the Inventory page after order completion via the Back Home button.

**Acceptance Criteria:**
- AC-1: Back Home navigates to Inventory page (TC-605)

---

## REQ-CKTC-03: Cart Clearing After Order Completion

**Description:** The system shall clear all cart contents once an order is completed.

**Acceptance Criteria:**
- AC-1: Cart is empty and badge is hidden after completion (TC-606)
- AC-2: Cart remains empty with no previous items on re-check (TC-607)

---

## REQ-CKTC-04: Checkout Completion Access Control

**Description:** The system shall prevent access to the Checkout Complete page, and prevent order resubmission, outside of a valid completed-checkout flow.

**Acceptance Criteria:**
- AC-1: Direct URL access without a completed order is blocked (TC-608)
- AC-2: Browser Back does not return to a resubmittable completed-order state (TC-609)

# Requirement Analysis – Logout & Session Management

## REQ-SESS-01: Logout Functionality

**Description:** The system shall provide a visible and functional logout option that terminates the user's session and returns them to the Login page.

**Acceptance Criteria:**
- AC-1: Logout option is visible in the navigation menu (TC-701)
- AC-2: Clicking Logout logs the user out and redirects to Login page (TC-702)
- AC-3: Login page is displayed correctly after logout (TC-707)

---

## REQ-SESS-02: Session Termination & Page Protection

**Description:** The system shall fully terminate the session on logout and prevent access to any previously authenticated page.

**Acceptance Criteria:**
- AC-1: Inventory page is inaccessible via direct URL after logout (TC-703)
- AC-2: Browser Back does not restore access to Inventory after logout (TC-704)
- AC-3: Checkout page is inaccessible after logout (TC-705)
- AC-4: No previously authenticated pages remain accessible after logout (TC-706)

---

## REQ-SESS-03: Cart Persistence & Isolation

**Description:** The system shall persist cart contents across a re-login for the same user, and maintain independent cart state per user session.

**Acceptance Criteria:**
- AC-1: Cart items persist for the same user after logout/login (TC-708)
- AC-2: Cart data is isolated between different user sessions (TC-709)

## 5. Non-Functional Requirements

This project's test design used SauceDemo's predefined special users (`problem_user`, `error_user`, `performance_glitch_user`, `visual_user`) to simulate different failure conditions. Because each of these users is exercised through ordinary functional test cases, the line between functional and non-functional testing is naturally blurred here — a login test, for example, is still a functional check, but when run against `performance_glitch_user` it also surfaces a performance-quality observation. Rather than duplicating these as separate non-functional requirements, they are cross-referenced below against the functional requirements that already cover them.

| Category | Related Functional Requirement(s) | Observation |
|---|---|---|
| Performance | REQ-AUTH-02, REQ-INV-05 | Noticeable load-time delay for `performance_glitch_user` |
| Usability / Responsiveness | REQ-INV-06, REQ-CART-01, REQ-CART-02, REQ-CKT2-05 | Unresponsive UI elements (buttons, links) for `error_user` |
| UI / Visual Consistency | REQ-INV-04, REQ-CART-03 | Layout and alignment inconsistencies for `visual_user` |

### Out of Scope

The following non-functional areas were not evaluated as part of this project:

- **Compatibility** — testing was limited to Chrome on a single OS; no cross-browser or cross-device testing was performed.
- **Load/Performance testing** — no dedicated load-testing tools were used; performance observations above are limited to manual, single-user page-load observation.

## 6. Assumptions

- SauceDemo does not provide official requirement documentation; all requirements in this document were reverse-engineered from observed application behavior rather than derived from a formal specification.
- Where application behavior was ambiguous or inconsistent (e.g., special-user quirks), the requirement was written to reflect the intended/expected behavior for standard usage, with deviations treated as defects rather than alternate valid requirements.
- Requirements reflect the application's behavior as observed in July 2026 and may not account for later changes to the live site.
