# BUG-012: Checkout Cannot Proceed for `problem_user`

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-407

**Related Test-Suite:** Checkout: Step One (Customer Information)

## Description

`problem_user` cannot proceed from Checkout Step One when attempting to complete the required customer information.

The Last Name field does not accept input correctly, preventing the required checkout information from being completed and blocking progression to the next checkout step.

## Preconditions

* SauceDemo is accessible.
* The user is logged in as `problem_user`.
* A product is in the cart.
* The user is on Checkout Step One.

## Steps to Reproduce

1. Log in using `problem_user / secret_sauce`.
2. Add a product to the cart.
3. Proceed to Checkout Step One.
4. Enter valid information in the First Name field.
5. Attempt to enter a valid Last Name.
6. Enter a valid ZIP/Postal Code.
7. Click **Continue**.

## Expected Result

The user should be able to complete all required customer information fields and click **Continue** to proceed to Checkout Step Two.

## Actual Result

The user cannot successfully complete the required customer information because the Last Name field does not accept the entered value correctly.

As a result, the user cannot proceed to the next checkout step.

## Evidence

![Bug evidence](../Screenshots/bug-012.png)

## Notes

This defect is the **downstream impact** of [BUG-011](bug-011-last-name-field-unresponsive.md). BUG-011 identifies the field-level defect where the Last Name field does not accept keyboard input correctly. 
BUG-012 focuses on the resulting functional impact: the user is unable to complete the required checkout information and proceed to Checkout Step Two.

The two defects share the same root cause but are tracked separately because they represent distinct user-facing failures at different levels: **field interaction** and **checkout progression**.

---

[← Previous Bug](bug-011-last-name-field-unresponsive.md)          [Next Bug →](bug-013.md)
