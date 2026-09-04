# BUG-006: **Add to Cart** Option Remains Functional for Invalid Product

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-209

**Related Test-Suite:** Product Detail

## Description

The invalid product page for product ID 123 displays a functional Add to Cart option. The nonexistent product can be added to the cart and the user can proceed through the checkout flow with it.

## Preconditions

* User is logged in to SauceDemo.
* User is on the invalid product page for product ID `123`.

## Steps to Reproduce

1. Open the invalid product page using product ID 123.
2. Observe that an Add to Cart option is displayed.
3. Click Add to Cart.
4. Open the Cart.
5. Verify that the invalid product has been added.
6. Proceed to Checkout.
7. Complete the required checkout information and continue through the checkout flow.

## Expected Result

The invalid product page should not provide a functional Add to Cart option. A nonexistent product should not be added to the cart or be allowed to proceed through the checkout flow.

## Actual Result

The invalid product page displays a functional Add to Cart option. The nonexistent product is added to the cart, and the user can proceed through the checkout flow with it.

## Evidence

![Bug evidence](../Screenshots/bug-006.png)

## Notes

The defect affects the integrity of the shopping flow because a product that does not exist can be treated as a valid cart item and proceed to checkout.

[← Previous Bug](bug-005-button-unresponsive.md)          [Next Bug →](bug-007-incorrect-product-shown-in-product-detail.md)
