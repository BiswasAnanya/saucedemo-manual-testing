# BUG-016: Completed Order Can Be Resubmitted After Browser Back

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-609

**Related Test-Suite:** Checkout: Complete

## Description

After successfully completing an order and returning to the Home page, using the browser Back button returns the user to the previous completed-order state.

The stale completed-order state remains actionable, allowing the order to be submitted again.

## Preconditions

* SauceDemo is accessible.
* The user is logged in.
* A product is available for purchase.

## Steps to Reproduce

1. Log in to SauceDemo.
2. Add a product to the cart.
3. Complete the checkout process successfully.
4. Confirm that the Checkout Complete page is displayed.
5. Click **Back Home**.
6. Press the browser **Back** button.
7. Observe the resulting page.
8. Attempt to submit the order again.

## Expected Result

After returning to the Home page, the browser Back action should not restore an actionable completed-checkout state.

The application should prevent the user from returning to a stale completed-order state or resubmitting the previously completed order.

## Actual Result

The browser Back button returns the user to the completed-order state, where the order can be resubmitted.

This allows the previously completed checkout flow to be submitted again.

## Evidence

![Bug evidence](../Screenshots/bug-016.png)

## Notes

This defect is different from the direct-access state-validation issues covered by BUG-010, BUG-013, and BUG-015. 
Those defects concern accessing protected checkout states without satisfying their prerequisites. BUG-016 concerns stale browser history after a successfully completed order and the resulting ability to resubmit the completed checkout.

---

[← Previous Bug](bug-015-checkout-complete-direct-access.md)          [Next Bug →](bug-017-cross-user-cart-data-isolation.md)
