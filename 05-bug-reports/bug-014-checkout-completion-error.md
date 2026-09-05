# BUG-014: `error_user` Cannot Complete Checkout from Overview

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-512

**Related Test-Suite:** Checkout: Step Two (Overview)

## Description

`error_user` is unable to complete the checkout process from the Checkout Overview page.

After valid customer information has been entered and the user reaches Checkout Step Two, clicking **Finish** does not successfully complete the order or navigate the user to the Checkout Complete page.

## Preconditions

* SauceDemo is accessible.
* The user is logged in as `error_user`.
* At least one product has been added to the cart.
* Valid checkout information is available.
* The user is on Checkout Step Two.

## Steps to Reproduce

1. Log in using `error_user / secret_sauce`.
2. Add a product to the cart.
3. Open the Cart page and click **Checkout**.
4. Enter the following valid customer information:

   * First Name: `John`
   * Last Name: `Doe`
   * Zip/Postal Code: `12345`
5. Click **Continue** to reach Checkout Step Two.
6. Click **Finish**.
7. Observe the resulting page.

## Expected Result

Clicking **Finish** should successfully complete the order, navigate the user to `checkout-complete.html`, and display the order confirmation message:

**Thank you for your order!**

## Actual Result

After clicking **Finish**, `error_user` cannot complete the order and does not reach the Checkout Complete page.

## Evidence

![Bug evidence](../Screenshots/bug-014.png)

## Notes

This defect is separate from other `error_user` defects because it affects the checkout completion workflow. 
For example, BUG-008 concerns the Remove button in the Shopping Cart, while BUG-015 concerns completing an order from the Checkout Overview page. 
Although both defects affect `error_user`, they involve different application functions and should therefore be tracked separately.

---

[← Previous Bug](bug-013-direct-checkout-step-two.md)          [Next Bug →](bug-015.md)
