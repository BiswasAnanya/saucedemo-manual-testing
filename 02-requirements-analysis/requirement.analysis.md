# Requirement Analysis for SauceDemo Application

## Purpose & Overview

The purpose of this requirements analysis is to establish a clear, testable, and traceable requirement baseline for the [SauceDemo](https://www.saucedemo.com/) application. The requirements define the expected functional behavior, business rules, validation rules, navigation behavior, and system responses used as the basis for test design.

Because [SauceDemo](https://www.saucedemo.com/) does not provide a formal requirements specification, the requirements in this document have been back-traced from observable application features, business behavior, user workflows, validation rules, navigation flows, and expected system responses. They provide the reference baseline for evaluating application behavior and for maintaining traceability throughout the QA process.

[SauceDemo](https://www.saucedemo.com/) (Swag Labs) is a sample e-commerce web application used for QA practice. It covers core online-shopping workflows such as- login, product browsing, cart management, checkout, and logout; along with a set of predefined users that simulate different application behaviors (`standard_user`, `locked_out_user`, `problem_user`, `error_user`, `performance_glitch_user`, `visual_user`).

Reference: Test Plan [TP-SAUCEDEMO-2026-001](../01-test-plan/test-plan.md)

## Functional Requirements

### Authentication / Login

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-AUTH-01 | System shall authenticate users based on username<br>and password, allowing valid predefined users to log in <br> and rejecting invalid attempts with appropriate error feedback. | Valid&nbsp;credentials&nbsp;🠂&nbsp;login&nbsp;succeeds<br>Wrong&nbsp;password&nbsp;🠂&nbsp;rejected&nbsp;with&nbsp;error<br>Blank&nbsp;username&nbsp;🠂&nbsp;required-field&nbsp;error<br>Unregistered&nbsp;credentials&nbsp;🠂&nbsp;rejected<br>Locked-out&nbsp;account&nbsp;🠂&nbsp;login&nbsp;blocked |
| REQ‑AUTH‑02 | System shall load the Inventory page within an<br>acceptable response time following a successful login. | Inventory&nbsp;page&nbsp;loads&nbsp;within&nbsp;acceptable&nbsp;time |
| REQ‑AUTH‑03 | System shall restrict access to authenticated pages<br>unless a valid session exists. | No&nbsp;session&nbsp;🠂&nbsp;redirected&nbsp;to&nbsp;Login&nbsp;page |



### Product Inventory

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ‑INV‑01 | System shall display the Inventory page after login<br>and allow navigation to and from individual<br>product details. | Inventory&nbsp;page&nbsp;loads&nbsp;after&nbsp;login<br>Clicking&nbsp;a&nbsp;product&nbsp;name&nbsp;navigates&nbsp;to&nbsp;its&nbsp;detail&nbsp;page<br>Returning&nbsp;from&nbsp;detail&nbsp;page&nbsp;retains&nbsp;previous&nbsp;sort&nbsp;order |
| REQ-INV-02 | System shall allow products to be sorted by price<br>and name, and correctly reorder them based on<br>the selected option. | Sorting&nbsp;by&nbsp;price&nbsp;low🠂high&nbsp;reorders&nbsp;correctly<br>Sorting&nbsp;by&nbsp;price&nbsp;high🠂low&nbsp;reorders&nbsp;correctly<br>Sorting&nbsp;by&nbsp;name&nbsp;A🠂Z&nbsp;reorders&nbsp;correctly<br>Sorting&nbsp;by&nbsp;name&nbsp;Z🠂A&nbsp;reorders&nbsp;correctly |
| REQ-INV-03 | System shall display the correct image for each<br>product on the Inventory page. | All&nbsp;products&nbsp;show&nbsp;valid&nbsp;images,&nbsp;no&nbsp;broken/missing&nbsp;icons<br>Each&nbsp;product&nbsp;displays&nbsp;its&nbsp;corresponding&nbsp;image |
| REQ-INV-04 | System shall present a consistent, correctly<br>aligned layout on the Inventory page. | Layout,&nbsp;spacing,&nbsp;and&nbsp;alignment&nbsp;are&nbsp;consistent<br>Product&nbsp;cards&nbsp;and&nbsp;controls&nbsp;are&nbsp;correctly&nbsp;positioned |
| REQ-INV-05 | System shall load the Inventory page within an<br>acceptable response time. | Inventory&nbsp;page&nbsp;loads&nbsp;within&nbsp;acceptable&nbsp;response&nbsp;time |
| REQ-INV-06 | System shall ensure all interactive elements on the<br>Inventory page (buttons, menu links) respond<br>correctly. | All&nbsp;Add&nbsp;to&nbsp;Cart&nbsp;buttons&nbsp;are&nbsp;responsive<br>Burger&nbsp;Menu&nbsp;options&nbsp;respond&nbsp;correctly<br>About&nbsp;link&nbsp;redirects&nbsp;to&nbsp;the&nbsp;expected&nbsp;destination |




### Product Detail

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-DET-01 | System shall navigate to the correct product detail page and display accurate, matching product information. | Clicking&nbsp;a&nbsp;product&nbsp;opens&nbsp;its&nbsp;detail&nbsp;page<br>Product&nbsp;name&nbsp;on&nbsp;detail&nbsp;page&nbsp;matches&nbsp;the&nbsp;selected&nbsp;item<br>Product&nbsp;information&nbsp;matches&nbsp;the&nbsp;selected&nbsp;product |
| REQ‑DET‑02 | System shall display all required product information completely and correctly on the detail page. | All&nbsp;required&nbsp;elements&nbsp;(image,&nbsp;name,&nbsp;description,&nbsp;price,&nbsp;buttons)&nbsp;are&nbsp;visible<br>Product&nbsp;description&nbsp;displays&nbsp;fully,&nbsp;without&nbsp;truncation<br>Product&nbsp;image&nbsp;loads&nbsp;correctly |
| REQ‑DET‑03 | System shall allow adding and removing products to/from the cart directly from the detail page. | Add&nbsp;to&nbsp;Cart&nbsp;adds&nbsp;product&nbsp;and&nbsp;updates&nbsp;button/badge<br>Remove&nbsp;removes&nbsp;product&nbsp;and&nbsp;updates&nbsp;button/badge |
| REQ‑DET‑04 | System shall gracefully handle access to invalid or non-existent products and prevent them from proceeding through checkout. | Invalid&nbsp;product&nbsp;URL&nbsp;displays&nbsp;"ITEM&nbsp;NOT&nbsp;FOUND"<br>Invalid&nbsp;products&nbsp;cannot&nbsp;proceed&nbsp;through&nbsp;the&nbsp;checkout&nbsp;flow |


### Shopping Cart

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ-CART-01 | System shall allow users to add one or more<br>products to the cart, updating the button state<br>and cart badge accordingly. | Single,&nbsp;multiple,&nbsp;and&nbsp;all&nbsp;products&nbsp;can&nbsp;be&nbsp;added<br>Cart&nbsp;badge&nbsp;updates&nbsp;correctly&nbsp;when&nbsp;products&nbsp;are&nbsp;added<br>Product&nbsp;data&nbsp;and&nbsp;image&nbsp;remain&nbsp;accurate |
| REQ-CART-02 | System shall allow users to remove products from<br>the cart, updating the button state and cart<br>badge accordingly. | Removing&nbsp;a&nbsp;product&nbsp;updates&nbsp;button&nbsp;and&nbsp;badge<br>Removed&nbsp;products&nbsp;no&nbsp;longer&nbsp;appear&nbsp;in&nbsp;the&nbsp;cart |
| REQ-CART-03 | System shall display the Cart page with correct<br>layout, alignment, and positioning of elements. | Cart&nbsp;layout&nbsp;is&nbsp;correctly&nbsp;aligned<br>Cart&nbsp;icons&nbsp;are&nbsp;correctly&nbsp;positioned<br>Checkout&nbsp;button&nbsp;is&nbsp;correctly&nbsp;positioned |
| REQ‑CART‑04 | System shall prevent users from proceeding to<br>checkout when the cart is empty. | Checkout&nbsp;is&nbsp;blocked&nbsp;when&nbsp;cart&nbsp;is&nbsp;empty |


### Checkout Step One (Customer Information)

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ‑CKT1‑01 | System shall display the Checkout Step One page<br>with all required customer information fields and<br>navigation controls. | Checkout&nbsp;Step&nbsp;One&nbsp;page&nbsp;loads&nbsp;with&nbsp;correct&nbsp;title<br>All&nbsp;required&nbsp;fields&nbsp;and&nbsp;buttons&nbsp;are&nbsp;displayed |
| REQ‑CKT1‑02 | System shall validate customer information fields<br>and allow progression only when valid data<br>is provided. | Valid&nbsp;information&nbsp;allows&nbsp;progression&nbsp;to&nbsp;Step&nbsp;Two<br>Empty&nbsp;fields&nbsp;are&nbsp;rejected&nbsp;with&nbsp;a&nbsp;required-field&nbsp;error |
| REQ‑CKT1‑03 | System shall allow users to cancel out of Checkout<br>Step One and return to the Cart page without<br>losing cart contents. | Cancel&nbsp;returns&nbsp;to&nbsp;Cart&nbsp;page&nbsp;with&nbsp;items&nbsp;unchanged |
| REQ-CKT1-04 | System shall correctly accept and register<br>keyboard input into each customer<br>information field. | First&nbsp;Name&nbsp;field&nbsp;accepts&nbsp;keyboard&nbsp;input&nbsp;correctly<br>Last&nbsp;Name&nbsp;field&nbsp;accepts&nbsp;keyboard&nbsp;input&nbsp;correctly<br>ZIP/Postal&nbsp;Code&nbsp;field&nbsp;accepts&nbsp;keyboard&nbsp;input&nbsp;correctly<br>Valid&nbsp;input&nbsp;in&nbsp;all&nbsp;fields&nbsp;allows&nbsp;progression&nbsp;to&nbsp;the&nbsp;next&nbsp;step |
| REQ‑CKT1‑05 | System shall prevent access to Checkout Step One<br>when the cart is empty. | Direct&nbsp;URL&nbsp;access&nbsp;is&nbsp;blocked&nbsp;when&nbsp;cart&nbsp;is&nbsp;empty |


### Checkout Step Two (Overview)

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ‑CKT2‑01 | System shall display the Checkout Overview page<br>only after valid customer information has been<br>submitted, and shall block direct access when<br>the cart is empty. | Overview&nbsp;page&nbsp;loads&nbsp;after&nbsp;valid&nbsp;Step&nbsp;One&nbsp;submission<br>Direct&nbsp;URL&nbsp;access&nbsp;is&nbsp;blocked&nbsp;when&nbsp;cart&nbsp;is&nbsp;empty |
| REQ‑CKT2‑02 | System shall accurately display all cart items,<br>their details, and quantities on the<br>Overview page. | All&nbsp;cart&nbsp;items&nbsp;are&nbsp;listed&nbsp;with&nbsp;correct&nbsp;details<br>Item&nbsp;details&nbsp;match&nbsp;what&nbsp;was&nbsp;added&nbsp;to&nbsp;cart<br>Item&nbsp;quantity&nbsp;is&nbsp;displayed&nbsp;correctly |
| REQ‑CKT2‑03 | System shall display dummy payment and shipping<br>information on the Overview page. | Payment&nbsp;Information&nbsp;section&nbsp;is&nbsp;displayed<br>Shipping&nbsp;Information&nbsp;section&nbsp;is&nbsp;displayed |
| REQ‑CKT2‑04 | System shall correctly calculate and display the<br>item total, tax, and overall total. | Price&nbsp;Total&nbsp;section&nbsp;is&nbsp;displayed<br>Item&nbsp;Total&nbsp;equals&nbsp;the&nbsp;exact&nbsp;sum&nbsp;of&nbsp;item&nbsp;prices |
| REQ-CKT2-05 | System shall allow users to complete or cancel<br>the order from the Overview page. | Finish&nbsp;completes&nbsp;the&nbsp;order&nbsp;and&nbsp;navigates&nbsp;to&nbsp;confirmation<br>Cancel&nbsp;returns&nbsp;to&nbsp;Inventory&nbsp;with&nbsp;cart&nbsp;unchanged |



### Checkout Complete

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ‑CKTC‑01 | System shall display the Checkout Complete page with the correct title, confirmation message, and navigation elements after order completion. | Page&nbsp;loads&nbsp;with&nbsp;correct&nbsp;title&nbsp;after&nbsp;Finish<br>Confirmation&nbsp;message&nbsp;is&nbsp;displayed<br>Confirmation&nbsp;sub-text&nbsp;is&nbsp;displayed<br>Back&nbsp;Home&nbsp;button&nbsp;is&nbsp;visible |
| REQ‑CKTC‑02 | System shall allow users to return to the<br>Inventory page after order completion via the Back Home button. | Back&nbsp;Home&nbsp;navigates&nbsp;to&nbsp;Inventory&nbsp;page |
| REQ‑CKTC‑03 | System shall clear all cart contents once an order is completed. | Cart&nbsp;is&nbsp;empty&nbsp;and&nbsp;badge&nbsp;is&nbsp;hidden&nbsp;after&nbsp;completion<br>Cart&nbsp;remains&nbsp;empty&nbsp;with&nbsp;no&nbsp;previous&nbsp;items&nbsp;on&nbsp;re-check |
| REQ‑CKTC‑04 | System shall prevent access to the Checkout<br>Complete page, and prevent order resubmission, outside of a valid completed-checkout flow. | Direct&nbsp;URL&nbsp;access&nbsp;without&nbsp;a&nbsp;completed&nbsp;order&nbsp;is&nbsp;blocked<br>Browser&nbsp;Back&nbsp;does&nbsp;not&nbsp;return&nbsp;to&nbsp;a&nbsp;resubmittable&nbsp;completed-order&nbsp;state |



### Logout & Session Management

| Req ID | Requirement | Acceptance Criteria |
|---|---|---|
| REQ‑SESS‑01 | System shall provide a visible and functional logout option that terminates the user's session and returns them to the Login page. | Logout&nbsp;option&nbsp;is&nbsp;visible&nbsp;in&nbsp;the&nbsp;navigation&nbsp;menu<br>Clicking&nbsp;Logout&nbsp;logs&nbsp;the&nbsp;user&nbsp;out&nbsp;and&nbsp;redirects&nbsp;to&nbsp;Login&nbsp;page<br>Login&nbsp;page&nbsp;is&nbsp;displayed&nbsp;correctly&nbsp;after&nbsp;logout |
| REQ‑SESS‑02 | System shall fully terminate the session on logout and prevent access to any previously authenticated page. | Inventory&nbsp;page&nbsp;is&nbsp;inaccessible&nbsp;via&nbsp;direct&nbsp;URL&nbsp;after&nbsp;logout<br>Browser&nbsp;Back&nbsp;does&nbsp;not&nbsp;restore&nbsp;access&nbsp;to&nbsp;Inventory&nbsp;after&nbsp;logout<br>Checkout&nbsp;page&nbsp;is&nbsp;inaccessible&nbsp;after&nbsp;logout<br>No&nbsp;previously&nbsp;authenticated&nbsp;pages&nbsp;remain&nbsp;accessible&nbsp;after&nbsp;logout |
| REQ‑SESS‑03 | System shall persist cart contents across a re-login for the same user, and maintain independent cart state per user session. | Cart&nbsp;items&nbsp;persist&nbsp;for&nbsp;the&nbsp;same&nbsp;user&nbsp;after&nbsp;logout/login<br>Cart&nbsp;data&nbsp;is&nbsp;isolated&nbsp;between&nbsp;different&nbsp;user&nbsp;sessions |


## Non-Functional Observations

This project's test design used SauceDemo's predefined special users (`problem_user`, `error_user`, `performance_glitch_user`, `visual_user`) to simulate different failure conditions. Because each of these users is exercised through ordinary functional test cases, the line between functional and non-functional testing is naturally blurred here; a login test, for example, is still a functional check, but when run against `performance_glitch_user` it also surfaces a performance-quality observation. Rather than duplicating these as separate non-functional requirements, they are cross-referenced below against the functional requirements that already cover them.

| Category | Related Functional Requirement(s) | Observation |
|---|---|---|
| Performance | REQ‑AUTH‑02, REQ‑INV‑05 | Noticeable&nbsp;load-time&nbsp;delay&nbsp;for&nbsp;`performance_glitch_user` |
| Usability / Responsiveness | REQ‑INV‑06, REQ‑CART‑01, REQ‑CART‑02, REQ‑CKT2‑05 | Unresponsive&nbsp;UI&nbsp;elements&nbsp;(buttons,&nbsp;links)&nbsp;for&nbsp;`error_user` |
| UI / Visual Consistency | REQ‑INV‑04, REQ‑CART‑03 | Layout&nbsp;and&nbsp;alignment&nbsp;inconsistencies&nbsp;for&nbsp;`visual_user` |

## Out of Scope

- **Compatibility:** No cross-browser or cross-device testing was performed.
- **Load/Performance testing:** Performance observations were limited to manual, single-user page-load checks.

## Assumptions

- SauceDemo does not provide official requirement documentation; requirements were reverse-engineered from observed application behavior.
- Where behavior was ambiguous or inconsistent, requirements reflect the intended behavior for standard usage, with deviations treated as defects.
- Requirements reflect observations made in August 2026 and may not account for later changes to the live site.
