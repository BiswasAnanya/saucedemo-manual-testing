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


## 5. Non-Functional Requirements

| Requirement ID | Category | Requirement | Priority | Source / Observation |
|---|---|---|---|---|
| NFR-001 | Performance | | | |
| NFR-002 | Usability | | | |
| NFR-003 | UI / Visual | | | |
| NFR-004 | Compatibility | | | |

## 6. Assumptions and Limitations

- [Placeholder]
- [Placeholder]
- [Placeholder]
