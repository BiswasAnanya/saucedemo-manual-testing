# BUG-006: Invalid Product Causes Checkout to Become Unresponsive

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-209

**Related Test-Suite:** Product Detail

## Description

An invalid product can be added to the cart from its Product Detail page. The user can then enter Checkout Step One, but proceeding to Checkout Step Two causes the checkout page to become blank and unresponsive.

## Preconditions

* User is logged in to SauceDemo.
* User is on the invalid product page for product ID `123`.

## Steps to Reproduce

1. Open the invalid product page using product ID `123`.
2. Click **Add to Cart**.
3. Open the Cart and verify that the invalid product has been added.
4. Proceed to Checkout.
5. Enter valid customer information on Checkout Step One.
6. Click **Continue**.
7. Observe Checkout Step Two.
8. Attempt to navigate back using the browser Back button.

## Expected Result

The invalid product should not be added to the cart or allowed to proceed through the checkout flow.

If an invalid product somehow reaches checkout, the application should handle the condition gracefully and keep the checkout flow functional.

## Actual Result

The invalid product is added to the cart and the user can proceed to Checkout Step One.

After entering valid customer information and clicking **Continue**, Checkout Step Two displays a blank page and becomes unresponsive. Using the browser Back button changes the URL, but the page remains blank and the application does not recover.

The session can only be recovered by closing the browser or logging in again.

## Evidence

![Bug evidence](../Screenshots/bug-006.png)

## Notes

The defect originates from allowing an invalid product to enter the cart, but the most severe impact occurs when the user reaches Checkout Step Two, where the application becomes effectively unusable for the current session.


[← Previous Bug](bug-005-button-unresponsive.md)          [Next Bug →](bug-007-incorrect-product-association.md)
