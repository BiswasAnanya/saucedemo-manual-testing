# BUG-010: Checkout Allowed with Empty Cart

**Status:** Open

**Severity:** High

**Priority:** P2

**Related Test-Case:** TC-309

**Related Test-Suite:** Shopping Cart

## Description

The application `standard_user` to proceed to the Checkout page after removing all products from the cart, even though the cart is empty.

## Preconditions

* User is logged in as `standard_user`.
* Inventory page is displayed.
* Cart contains multiple products.

## Steps to Reproduce

1. Log in as `standard_user`.
2. Add multiple products to the cart.
3. Select **Cart**.
4. Remove all products from the cart.
5. Click **Checkout**.
6. Observe the resulting page.

## Expected Result

The user should not be allowed to proceed to Checkout when the cart is empty. The application should prevent the checkout flow from continuing until at least one product is present in the cart.

## Actual Result

The user can proceed to the **Checkout** page even though the cart is empty. 

## Evidence

![Bug evidence](../Screenshots/bug-010.png)


---

[← Previous Bug](bug-009-cart-layout-inconsistency.md)          [Next Bug →](bug-011.md)

