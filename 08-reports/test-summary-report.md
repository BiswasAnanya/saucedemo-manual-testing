## TBA

| Theme                                                                      | Test Cases                                     | Severity Signal                                                                        |
| -------------------------------------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------------------------------- |
| Checkout flow state-validation bypass                                      | TC-309, TC-410, TC-502, TC-608                 | High — business rule not consistently enforced at multiple entry points                |
| Cross-user cart data isolation failure                                     | TC-709                                         | Critical — cart data leaks across user sessions                                        |
| `problem_user` product data/image mismatch                                 | TC-107, TC-210, TC-305, TC-512                 | Medium — consistent issue isolated to one test user                                    |
| `problem_user` Checkout Step One field interaction failure                 | TC-408, TC-409                                 | High — Last Name input is not handled correctly, preventing valid checkout progression |
| Post-order state/caching (browser Back resubmission)                       | TC-609                                         | High — potential duplicate order submission                                            |
| Special-user functional breakage (`error_user`, `performance_glitch_user`) | TC-008, TC-110, TC-111, TC-306, TC-307, TC-312, TC-513 | Varies — defects simulate degraded, broken, or inconsistent application behavior among special test users |
