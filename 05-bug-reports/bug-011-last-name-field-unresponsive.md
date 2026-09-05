# BUG-011: Last Name Field Unresponsive for `problem_user`

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-406

**Related Test-Suite:** Checkout: Step One (Customer Information)

## Description

For `problem_user`, the Last Name field on Checkout Step One does not accept keyboard input correctly. When the user attempts to enter a Last Name, the entered value is instead applied to the First Name field.

This indicates that the Last Name input field is not functioning independently as expected.

## Preconditions

* SauceDemo is accessible.
* The user is logged in as `problem_user`.
* A product has been added to the cart.
* The user is on Checkout Step One.

## Steps to Reproduce

1. Log in using `problem_user / secret_sauce`.
2. Add a product to the cart.
3. Open the Cart page.
4. Proceed to Checkout Step One.
5. Enter a value in the First Name field.
6. Click or focus on the Last Name field.
7. Attempt to enter a Last Name.
8. Observe which field receives the entered text.

## Expected Result

The Last Name field should accept keyboard input independently and display the entered value within the Last Name field.

The First Name field should remain unchanged when entering data into the Last Name field.

## Actual Result

The Last Name field does not accept keyboard input correctly. The value entered is instead applied to the First Name field.

As a result, the Last Name field remains empty or does not contain the intended value.

## Evidence

![Bug evidence](../Screenshots/bug-011.png)

## Notes

This defect is the **root cause** of the checkout progression failure reported in BUG-012. TC-406 verifies the field-level defect itself, while TC-407 verifies the resulting inability to proceed through checkout. 
Although both defects originate from the same underlying issue, they are tracked separately because they represent two distinct user-visible failures: an unresponsive Last Name field and a blocked checkout progression.

---

[← Previous Bug](bug-010-checkout-with-empty-cart.md)          [Next Bug →](bug-012-checkout-progression-blocked.md)
