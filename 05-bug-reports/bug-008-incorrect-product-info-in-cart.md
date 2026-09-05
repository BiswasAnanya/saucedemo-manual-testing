# BUG-008: Incorrect Product Information in Cart for problem_user

**Status:** Open

**Severity:** Medium

**Priority:** P2

**Related Test-Case:** TC-305

**Related Test-Suite:** Shopping Cart

## Description

For `problem_user`, the product information displayed in the cart is incorrectly associated with the selected product.

## Preconditions

* User is logged in as `problem_user`.
* Inventory page is displayed.
* Cart is empty.

## Steps to Reproduce

1. Add **Sauce Labs Backpack** to the cart.
2. Open the Cart.
3. Verify the product name and image.

## Expected Result

The cart should contain **Sauce Labs Backpack** with the correct product information and image.

## Actual Result

Product information and/or the product image is incorrectly associated with the selected product for `problem_user`.

## Evidence

![Bug evidence](../Screenshots/bug-008.png)

## Notes

This defect is related to [BUG-007](bug-007-incorrect-product-image-in-detail.md), which reports incorrect product information on the Product Detail page for problem_user. 
The two defects may share the same underlying product-association or product-mapping issue, as the incorrect product information appears both on the Product Detail page and in the Cart.
However, the defects are reported separately because they were observed in different application areas:

BUG-007: Incorrect product displayed on the Product Detail page.

BUG-008: Incorrect product information or image displayed in the Cart.

Further investigation is required to confirm whether both issues have the same root cause.

---

[← Previous Bug](bug-007-incorrect-product-image-in-detail.md)          [Next Bug →](BUG-009.md)
