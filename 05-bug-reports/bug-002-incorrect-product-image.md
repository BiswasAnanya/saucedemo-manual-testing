# BUG-002: Incorrect Product Images Displayed for `problem_user`

**Status:** Open

**Severity:** Medium

**Priority:** P2

**Related Test-Case:** TC-107

**Related Test-Suite:** Product Inventory

## Description

Product images doesn't adhere with products when using `problem_user`. The displayed image does not consistently match the corresponding product name.

## Preconditions

* Browser is open on the SauceDemo Login page.

## Steps to Reproduce

1. Log in with `problem_user` / `secret_sauce`.
2. Navigate to the Inventory page.
3. Review the product names and the associated images displayed with them.
4. Compare each image with the corresponding product.

## Expected Result

Each product should display its correct corresponding image.

## Actual Result

Product images doesn't adhere/correspond with the mentioned products.

## Evidence

![Bug evidence](../Screenshots/bug-002.png)

## Notes

The issue affects the accuracy of product information presented to the user.

[← Previous Bug](BUG-001.md) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [Next Bug →](BUG-003.md)
