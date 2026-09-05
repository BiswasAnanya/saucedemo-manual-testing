# BUG-015: Checkout Complete Page Accessible Without Completed Order

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-608

**Related Test-Suite:** Checkout: Complete

## Description

The application allows a logged-in user to directly access the Checkout Complete page without completing an order.

The page is accessible through its direct URL and displays the order confirmation message even though no order has been completed.

## Preconditions

* SauceDemo is accessible.
* The user is logged in.
* No order has been completed during the current session.

## Steps to Reproduce

1. Log in to SauceDemo.
2. Ensure that no order has been completed.
3. Navigate directly to `/checkout-complete.html`.
4. Observe the resulting page.

## Expected Result

The application should prevent access to the Checkout Complete page when no order has been completed.

The user should be redirected to an appropriate page or shown an appropriate error message indicating that the checkout process has not been completed.

## Actual Result

The Checkout Complete page is accessible directly without a completed order and displays the message:

**Thank you for your order!**

## Evidence

![Bug evidence](../Screenshots/bug-015.png)

## Notes

This defect is related to other checkout state-validation issues, such as BUG-010 and BUG-013, but affects a different stage of the checkout workflow. 
BUG-015 specifically concerns unauthorized access to the final Checkout Complete state without a completed order.

---

[← Previous Bug](bug-014-checkout-completion-error.md)          [Next Bug →](bug-016-completed-order-resubmission.md)
