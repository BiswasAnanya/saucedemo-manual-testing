# BUG-009: Cart Layout Inconsistencies for `visual_user`

**Status:** Open

**Severity:** Low

**Priority:** P3

**Related Test-Case:** TC-308

**Related Test-Suite:** Shopping Cart

## Description

The Cart page contains visual and layout inconsistencies when using `visual_user`. The cart interface is not presented according to the expected visual layout, including incorrect alignment of the cart icon and incorrect positioning of the Checkout button.

## Preconditions

* Browser is open on the SauceDemo Login page.

## Steps to Reproduce

1. Log in with `visual_user / secret_sauce`.
2. Navigate to the Inventory page.
3. Add **Sauce Labs Bike Light** to the cart.
4. Open the Cart page.
5. Review the cart icon alignment, margins, spacing, and Checkout button position.

## Expected Result

The Cart page should maintain the expected layout, spacing, alignment, and visual presentation. The cart icon should be correctly aligned with the surrounding margins, and the Checkout button should appear in its expected position within the Cart layout.

## Actual Result

Visual/UI inconsistencies are present on the Cart page for `visual_user`. The cart icon appears misaligned relative to the expected margins, and the Checkout button is incorrectly positioned in the top-right corner.

## Evidence

![Bug evidence](../Screenshots/bug-009.png)

## Notes

Although this defect is similar in nature to BUG-004, the two defects affect different pages of the application. BUG-004 concerns the Inventory page, while BUG-009 concerns the Cart page. 
Tracking them separately provides clearer defect coverage and makes it easier to identify which page is affected.

[← Previous Bug](bug-008-remove-button-unresponsive.md)          [Next Bug →](bug-010-checkout-with-empty-cart.md)
