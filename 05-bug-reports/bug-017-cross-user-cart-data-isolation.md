# BUG-017: Cart Data Not Isolated Between User Sessions

**Status:** Open

**Severity:** Critical

**Priority:** P1

**Related Test-Case:** TC-709

**Related Test-Suite:** Logout/Session Handling

## Description

Cart data is not properly isolated between different SauceDemo user sessions.

Products added to the cart by one user remain in the cart after that user logs out and another user logs in. As a result, the newly authenticated user inherits the previous user's cart items.

## Preconditions

* SauceDemo is accessible.
* Multiple valid SauceDemo users are available.
* `standard_user` has an initially empty cart.

## Steps to Reproduce

1. Log in using `standard_user / secret_sauce`.
2. Add two products to the cart.
3. Open the Cart page and verify that the two products are present.
4. Log out.
5. Log in using `error_user` / `secret_sauce`.
6. Open the Cart page.
7. Observe the cart contents.
8. Repeat the login/logout process with `problem_user`, `performance_glitch_user`, and `visual_user`.

## Expected Result

Each user session should have an independent cart.

After logging in as a different user, the new user should not inherit products added to another user's cart.

## Actual Result

The same two products remain in the cart after logging in as `error_user`, `problem_user`, `performance_glitch_user`, and `visual_user`.

This exposes one user's cart data to other user sessions.

## Evidence

![Bug evidence](../Screenshots/bug-017.png)

## Notes

This defect affects cross-user data isolation and is distinct from other cart and checkout defects. The issue is not limited to a single user account because the previously added cart items persist across multiple user sessions.

The defect may expose one user's shopping state to another user and could potentially lead to unintended changes to or purchases from another user's cart.

---

[← Previous Bug](bug-016-completed-order-resubmission.md)          [Next Bug →](bug-018.md)
