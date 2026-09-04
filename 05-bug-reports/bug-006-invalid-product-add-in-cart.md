# BUG-006: **Add to Cart** Option Remains Functional for Invalid Product

**Status:** Open

**Severity:** Medium

**Priority:** P2

**Related Test-Case:** TC-209

**Related Test-Suite:** Product Detail

## Description

The invalid product page displays an **Add to Cart** option that remains functional even though the requested product does not exist.

## Preconditions

* User is logged in to SauceDemo.
* User is on the invalid product page for product ID `123`.

## Steps to Reproduce

1. Open the invalid product page using product ID `123`.
2. Check whether an **Add to Cart** option is displayed.
3. Click **Add to Cart**.
4. Observe the cart behavior.

## Expected Result

The invalid product page should not provide a functional **Add to Cart** option.

## Actual Result

The invalid product page displays a functional **Add to Cart** option.

## Evidence

![Bug evidence](../Screenshots/bug-006.png)

## Notes

The page correctly indicates that the requested product is invalid (doesn't exist in Inventory), but still exposes an actionable **Add to Cart** option.

[← Previous Bug](bug-005-button-unresponsive.md)          [Next Bug →](bug-007-incorrect-product-shown-in-product-detail.md)
