# BUG-002: Incorrect Product Images Displayed for `problem_user`

**Status:** Open

**Severity:** Medium

**Priority:** P2

**Related Test-Case:** TC-107

**Related Test-Suite:** Product Inventory

## Description

Product images doesn't adhere with products when using `problem_user`. The displayed image does not consistently match the corresponding product name. Rather every product displayed on the Inventory page uses the same image, regardless of the actual product. 

## Preconditions

* Browser is open on the SauceDemo Login page.

## Steps to Reproduce

1. Log in with `problem_user` / `secret_sauce`.
2. Navigate to the Inventory page.
3. Review the product names and the associated images displayed with them.
4. Compare each image with the corresponding product.

## Expected Result

Each product should display its correct corresponding image. 

Example:

* Sauce Labs Backpack → Backpack image
* Sauce Labs Bike Light → Bike Light image
* Sauce Labs Bolt T-Shirt → T-Shirt image
* Sauce Labs Onesie → Onesie image

## Actual Result

Product images doesn't adhere/correspond with the mentioned products. 
Although product names, descriptions, prices, and buttons are correct, every product card uses an identical image.

## Evidence

![Bug evidence](../Screenshots/bug-002.png)

## Notes

This defect is first observed on the Inventory page for `problem_user`. This defect can make the user select a wrong product and go forward with the order and checkout process, resulting into negative user-experience. The incorrect product information/image association originates at this stage and is subsequently carried through later stages of the shopping workflow. Downstream manifestations are covered by [BUG-007](bug-007-incorrect-product-association.md)

[← Previous Bug](bug-001-page-loading-delay.md) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [Next Bug →](bug-003-product-sorting-issue.md)
