# BUG-017: About Link Redirects to 404 Page

**Status:** Open

**Severity:** Medium

**Priority:** P2

**Related Test-Case:** TC-112

**Related Test-Suite:** Product Inventory

## Description

The **About** option in the Burger Menu does not redirect the user to the official Sauce Labs website as expected.

Instead, clicking the **About** link redirects the user to a **404 – Page Not Found** error page.

## Preconditions

* SauceDemo is accessible.
* The user is logged in.
* The Inventory page is displayed.

## Steps to Reproduce

1. Log in to SauceDemo.
2. Open the Burger Menu.
3. Click **About**.
4. Observe the resulting page.

## Expected Result

The user should be redirected to the official Sauce Labs website, and the destination page should load successfully.

## Actual Result

Clicking the **About** link redirects the user to a **404 – Page Not Found** error page instead of opening the Sauce Labs About page.

## Evidence

![Bug evidence](../Screenshots/bug-018.png)

## Notes

The About link does not fulfill its intended navigation function because the configured destination is unavailable and results in a 404 error.

---

[← Previous Bug](bug-017-cross-user-cart-data-isolation.md)          [Next Bug →](bug-018.md)
