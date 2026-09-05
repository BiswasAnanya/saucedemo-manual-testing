# BUG-001: Delayed Inventory Page Load for Performance Glitch User

**Status:** Open

**Severity:** Medium

**Priority:** P3

**Related Test-Cases:** TC-008, TC-110

**Related Test-Suite:** Authentication/Login

## Description

The Inventory page takes noticeably longer to load when logging in with `performance_glitch_user` compared with `standard_user`.
The login itself is successful, but the delay affects the transition from the Login page to the Inventory page.

## Preconditions

* Browser is open on the SauceDemo Login page.

## Steps to Reproduce

1. Enter username `performance_glitch_user`.
2. Enter password `secret_sauce`.
3. Click **Login**.
4. Measure the time taken for the Inventory page to become fully loaded.
5. Repeat the same steps using `standard_user` and compare the load time.

## Expected Result

User should successfully log in and the Inventory page should load within the defined acceptable response time.

## Actual Result

User successfully logs in, but the Inventory page takes noticeably longer (> 3 seconds) to load compared with standard_user.

## Evidence

TBA

## Notes

The slowdown appears to be specific to `performance_glitch_user`. The application remains usable once the Inventory page finishes loading, but the additional delay is noticeable during the login flow.

[Next Bug →](bug-002-incorrect-product-image-inventory.md)

