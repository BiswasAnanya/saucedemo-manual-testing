# BUG-005: Add to Cart Buttons Unresponsive for `error_user`

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-111

**Related Test-Suite:** Product Inventory

## Description

Three of the six Add to Cart buttons are unresponsive when using `error_user`.


## Preconditions
* Browser is open on the SauceDemo Login page.

## Steps to Reproduce

1. Log in with `error_user` / `secret_sauce`
2. Navigate to the Inventory page.
3. Scroll through the available products.
4. Click each Add to Cart button.
5. Observe the response from each button.

## Expected Result

All Add to Cart buttons should respond and add their corresponding products to the cart.

## Actual Result

Three of the six Add to Cart buttons are unresponsive and do not add the corresponding products to the cart.

## Evidence

![Bug evidence](../Screenshots/bug-005.png)

## Notes

The issue affects half of the available products and prevents those products from being added to the cart through the Inventory page.

[← Previous Bug](bug-004-layout-inconsistency.md) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [Next Bug →](bug-006-layout-inconsistency.md)
