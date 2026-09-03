## TBA



| Theme | Test Cases | Severity Signal |
|---|---|---|
| Checkout flow state-validation bypass | TC-309, TC-410, TC-502, TC-608 | High — business rule not enforced at 4 entry points |
| Cross-user cart data isolation failure | TC-709 | Critical — data leaks across sessions |
| `problem_user` product data/image mismatch | TC-107, TC-210, TC-305, TC-512 | Medium — consistent, isolated to one test user |
| Checkout Step One input validation gaps | TC-406, TC-407 | Medium — accepts invalid data formats |
| Post-order state/caching (browser Back resubmission) | TC-609 | High — potential duplicate order |
| Special-user functional breakage (`error_user`, `performance_glitch_user`) | TC-008, TC-110, TC-111, TC-306, TC-307, TC-513 | Varies — broadly simulates real degraded conditions |
