# BUG-008: Remove Button Unresponsive for `error_user`

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-307

**Related Test-Suite:** Shopping Cart

## Description

For `error_user`, the **Remove** button does not respond when attempting to remove a product from the cart from the Inventory page.

## Preconditions

* User is logged in as `error_user`.
* Inventory page is displayed.
* Cart is empty.

## Steps to Reproduce

1. Add a product to the cart.
2. Remain on the Inventory page.
3. Click **Remove** for the selected product.
4. Observe the cart badge and product state.

## Expected Result

The selected product should be removed from the cart and the cart badge should decrease accordingly.

## Actual Result

The **Remove** button is unresponsive. The product remains in the cart, and the cart badge/UI does not update correctly.

## Evidence

![Bug evidence](../Screenshots/bug-008.png)

## Notes

The defect prevents the user from removing the selected product through the Inventory page.

---

[← Previous Bug](bug-007-incorrect-product-association.md)          [Next Bug →](bug-009-cart-layout-inconsistency.md)
