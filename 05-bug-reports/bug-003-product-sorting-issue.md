# BUG-003: Product Sorting Does Not Change Order for `problem_user`

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-108

**Related Test-Suite:** Product Inventory

## Description

The product sorting controls do not change the product order when logged in as `problem_user`.

## Preconditions

* Browser is open on the SauceDemo Login page.

## Steps to Reproduce

1. Log in with `problem_user` / `secret_sauce`.
2. Navigate to the Inventory page.
3. Select **A-Z** and observe the product order.
4. Select **Z-A** and observe the product order.
5. Select **Price (low to high)** and observe the product order.
6. Select **Price (high to low)** and observe the product order.

## Expected Result

Products should be reordered correctly according to the selected sorting option.

## Actual Result

The product order does not change when different sorting options are selected.

## Evidence

![Bug evidence](../Screenshots/bug-003.png)

## Notes

The sorting control remains available, but selecting different options does not produce the expected change in product order.

[← Previous Bug](bug-002-incorrect-product-image-inventory.md) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [Next Bug →](bug-004-layout-inconsistency.md)
