# BUG-007: Incorrect Product Association for problem_user

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Cases:** TC-210, TC-305

**Related Test-Suites:** Product Detail, Shopping Cart

## Description

For `problem_user`, the application displays incorrect product information when selecting a product and carrying it through the shopping flow. The Product Detail page displays a different product than the one selected, and the incorrect product information is also reflected in the Cart.

## Preconditions

* User is logged in as `problem_user`.
* Inventory page is displayed.
* Cart is empty.

## Steps to Reproduce

1. Select **Sauce Labs Backpack** from the Inventory page.
2. Observe the Product Detail page.
3. Verify that the displayed product matches the selected product.
4. Add the product to the cart.
5. Open the Cart.
6. Verify the product name and image.

## Expected Result

The selected product should be displayed correctly on the Product Detail page and the same product, with the correct product information and image, should appear in the Cart.

## Actual Result

A different product is displayed on the Product Detail page instead of the selected **Sauce Labs Backpack**. The incorrect product information/image is also reflected in the Cart.

## Evidence

![Bug evidence](../Screenshots/bug-007.png)

## Notes

The defect affects product identification across multiple stages of the shopping flow and may result in the user viewing or purchasing a different product than the one originally selected.

---

[← Previous Bug](bug-006-invalid-product-add-in-cart.md)          [Next Bug →](bug-008-remove-button-unresponsive.md)
