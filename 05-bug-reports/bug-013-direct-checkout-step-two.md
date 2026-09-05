# BUG-013: Direct Access to Checkout Step Two with Empty Cart

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-502

**Related Test-Suite:** Checkout: Step Two (Overview)

## Description

The application allows `standard_user` to directly access the Checkout Step Two page when the cart is empty and Checkout Step One has not been completed.

This bypasses the expected checkout sequence and allows the user to reach the order overview page without satisfying the required checkout prerequisites.

## Preconditions

* SauceDemo is accessible.
* The user is logged in as `standard_user`.
* The cart is empty.
* Checkout Step One has not been completed.

## Steps to Reproduce

1. Log in using `standard_user / secret_sauce`.
2. Ensure that the cart is empty.
3. Navigate directly to `checkout-step-two.html`.
4. Observe the resulting page.

## Expected Result

The application should prevent access to Checkout Step Two when the cart is empty and Checkout Step One has not been completed.

The user should be redirected to an appropriate page or shown an appropriate error message indicating that the required checkout prerequisites have not been satisfied.

## Actual Result

The user can directly access the Checkout Step Two page with an empty cart without completing the previous checkout steps.

The application does not enforce the expected checkout sequence or cart prerequisite.

## Evidence

![Bug evidence](../Screenshots/bug-013.png)

## Notes

This defect is related to [BUG-010](bug-010-checkout-with-empty-cart.md), which covers the broader checkout flow state-validation issue for an empty cart. 
However, TC-502 verifies a distinct entry point and failure condition: direct access to **Checkout Step Two** without completing Checkout Step One.

The defects share the same underlying state-validation weakness but are tracked separately because they affect different checkout stages and represent distinct user-visible failures.

---

[← Previous Bug](bug-012-checkout-progression-blocked.md)          [Next Bug →](bug-014.md)
