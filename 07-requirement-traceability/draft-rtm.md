# Requirements Traceability Matrix (RTM) – SauceDemo

## Purpose

This document traces each requirement defined in the [Requirement Analysis](../02-requirement-analysis/requirement-analysis.md) to the test case(s) that validate it, records the execution status of each test case, and links any failure to its corresponding defect report. It serves as the single point of reference for verifying requirement coverage and understanding the current quality status of the application.

Reference: [Requirement Analysis](../02-requirement-analysis/requirement-analysis.md) | [Test Plan TP-SAUCEDEMO-2026-001](../01-test-plan/test-plan.md) | [Defect Reports](../05-bug-reports/)

---

## Authentication / Login

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-AUTH-01 | User Authentication | TC-001–007, TC-009, TC-010 | ✅ Passed | — |
| REQ-AUTH-02 | Login Performance | TC-008 | ❌ Failed | BUG-001 |
| REQ-AUTH-03 | Session Protection | TC-011 | ✅ Passed | — |



## Product Inventory

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-INV-01 | Inventory Page Display & Navigation | TC-101, TC-105, TC-106 | ✅ Passed | — |
| REQ-INV-02 | Product Sorting | TC-102, TC-103 | ✅ Passed | — |
| REQ-INV-02 | Product Sorting | TC-108 | ❌ Failed | BUG-003 |
| REQ-INV-03 | Product Image Accuracy | TC-104 | ✅ Passed | — |
| REQ-INV-03 | Product Image Accuracy | TC-107 | ❌ Failed | BUG-002 |
| REQ-INV-04 | UI/Visual Presentation | TC-109 | ❌ Failed | BUG-004 |
| REQ-INV-05 | Page Load Performance | TC-110 | ❌ Failed | BUG-001 |
| REQ-INV-06 | Interactive Element Responsiveness | TC-111 | ❌ Failed | BUG-005 |
| REQ-INV-06 | Interactive Element Responsiveness | TC-112 | ❌ Failed | BUG-018 |



## Product Detail

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-DET-01 | Product Detail Navigation & Accuracy | TC-201, TC-203 | ✅ Passed | — |
| REQ-DET-01 | Product Detail Navigation & Accuracy | TC-210 | ❌ Failed | BUG-007 |
| REQ-DET-02 | Product Detail Page Content | TC-202, TC-204, TC-205 | ✅ Passed | — |
| REQ-DET-03 | Cart Actions from Detail Page | TC-206, TC-207 | ✅ Passed | — |
| REQ-DET-04 | Invalid Product Handling | TC-208 | ✅ Passed | — |
| REQ-DET-04 | Invalid Product Handling | TC-209 | ❌ Failed | BUG-006 |



## Shopping Cart

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-CART-01 | Add Products to Cart | TC-301, TC-302, TC-304 | ✅ Passed | — |
| REQ-CART-01 | Add Products to Cart | TC-305 | ❌ Failed | BUG-007 |
| REQ-CART-01 | Add Products to Cart | TC-306 | ❌ Failed | BUG-005 |
| REQ-CART-02 | Remove Products from Cart | TC-303 | ✅ Passed | — |
| REQ-CART-02 | Remove Products from Cart | TC-307 | ❌ Failed | BUG-008 |
| REQ-CART-03 | Cart Page UI | TC-308 | ❌ Failed | BUG-009 |
| REQ-CART-04 | Checkout Eligibility | TC-309 | ❌ Failed | BUG-010 |



## Checkout Step One (Customer Information)

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-CKT1-01 | Checkout Step One Page & Form Display | TC-401, TC-402 | ✅ Passed | — |
| REQ-CKT1-02 | Customer Information Validation | TC-403, TC-404 | ✅ Passed | — |
| REQ-CKT1-03 | Checkout Navigation Controls | TC-405 | ✅ Passed | — |
| REQ-CKT1-04 | Form Field Input Handling | TC-406 | ❌ Failed | BUG-011 |
| REQ-CKT1-04 | Form Field Input Handling | TC-407 | ❌ Failed | BUG-012 |
| REQ-CKT1-05 | Checkout Access Restriction | TC-408 | ❌ Failed | BUG-010 |



## Checkout Step Two (Overview)

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-CKT2-01 | Checkout Overview Page Access | TC-501 | ✅ Passed | — |
| REQ-CKT2-01 | Checkout Overview Page Access | TC-502 | ❌ Failed | BUG-013 |
| REQ-CKT2-02 | Cart Item Accuracy on Overview | TC-503, TC-504, TC-505 | ✅ Passed | — |
| REQ-CKT2-03 | Payment & Shipping Information Display | TC-506, TC-507 | ✅ Passed | — |
| REQ-CKT2-04 | Order Total Calculation | TC-508, TC-509 | ✅ Passed | — |
| REQ-CKT2-05 | Order Completion & Cancellation | TC-510, TC-511 | ✅ Passed | — |
| REQ-CKT2-05 | Order Completion & Cancellation | TC-512 | ❌ Failed | BUG-014 |


## Checkout Complete

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-CKTC-01 | Checkout Complete Page Display | TC-601–604 | ✅ Passed | — |
| REQ-CKTC-02 | Post-Order Navigation | TC-605 | ✅ Passed | — |
| REQ-CKTC-03 | Cart Clearing After Order Completion | TC-606, TC-607 | ✅ Passed | — |
| REQ-CKTC-04 | Checkout Completion Access Control | TC-608 | ❌ Failed | BUG-015 |
| REQ-CKTC-04 | Checkout Completion Access Control | TC-609 | ❌ Failed | BUG-016 |



## Logout & Session Management

| Req ID | Requirement Summary | Test Case ID(s) | Execution Status | Defect ID |
|---|---|---|---|---|
| REQ-SESS-01 | Logout Functionality | TC-701, TC-702, TC-707 | ✅ Passed | — |
| REQ-SESS-02 | Session Termination & Page Protection | TC-703–706 | ✅ Passed | — |
| REQ-SESS-03 | Cart Persistence & Isolation | TC-708 | ✅ Passed | — |
| REQ-SESS-03 | Cart Persistence & Isolation | TC-709 | ❌ Failed | BUG-017 |



## Coverage Summary

- **Total Requirements:** 34
- **Total Test Cases:** 80
- **Passed:** 58
- **Failed:** 22
- **Requirement Coverage:** 100% (every requirement is mapped to at least one test case)
- **Total Unique Defects Traced:** 18 (BUG-001 through BUG-018), covering all 22 failed test cases
- **Defects Linked to Multiple Test Cases:** BUG-001 (TC-008, TC-110), BUG-005 (TC-111, TC-306), BUG-007 (TC-210, TC-305), BUG-010 (TC-309, TC-408)
