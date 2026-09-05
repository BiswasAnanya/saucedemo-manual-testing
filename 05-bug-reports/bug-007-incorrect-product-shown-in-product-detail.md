# BUG-007: Incorrect Product Displayed on Product Detail Page for `problem_user`

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-210

**Related Test-Suite:** Product Detail

## Description

The Product Detail page displays a different product from the one selected on the Inventory page when using `problem_user`.

## Preconditions

* User is logged in as `problem_user`.
* User is on the Inventory page.

## Steps to Reproduce

1. Log in with `problem_user` / `secret_sauce`.
2. Open the **Sauce Labs Backpack** from the Inventory page.
3. Verify the product displayed on the Product Detail page.

## Expected Result

The Product Detail page should display the same product that was selected from the Inventory page.

## Actual Result

The Product Detail page displays a different product instead of the selected **Sauce Labs Backpack**. 

## Evidence

![Bug evidence](../Screenshots/bug-007.png)

## Notes

The incorrect product association can cause users to view or purchase a product different from the one they originally selected.

[← Previous Bug](bug-006-invalid-product-add-in-cart.md)          [Next Bug →](BUG-008.md)
