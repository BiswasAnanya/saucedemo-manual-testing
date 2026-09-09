# SauceDemo Manual Testing Project

A comprehensive manual QA portfolio project demonstrating the end-to-end testing of the [SauceDemo](https://www.saucedemo.com/) e-commerce web application; including functional, negative, UI, and user-specific test scenarios.

The project simulates a structured software testing process covering test planning, requirement analysis, test design, smoke testing, test execution, defect reporting, traceability, and test summarization.

**Test Results at a glance:** 72.5% pass rate (58/80 passed) · 18 defects logged · 13 rated Critical/High severity

## 🖥️ Application Under Test

Application: SauceDemo

Website: https://www.saucedemo.com/

Type: Demo e-commerce web application


## 📑 Explore the Project

- [Test Plan](01-test-plan/test-plan.md) -> scope, approach, and strategy
- [Requirement Analysis](02-requirements-analysis/requirement.analysis.md) -> reverse-engineered functional requirements
- [Test Suites](03-test-suites/) -> 80 test cases across 8 feature suites
- [Smoke Test Suite](04-smoke-testing/smoke-test-suite.md) -> 10 test-cases for critical-path
- [Defect Reports](05-bug-reports/) -> 18 individual bug reports
- [Requirement Traceability Matrix](07-requirement-traceability/requirements-traceability-matrix.md) -> requirement ↔ test case ↔ defect mapping
- [Test Execution Report](08-reports/test-execution-report.md) -> full results, findings, and defect analysis
- [Test Summary Report](08-reports/test-summary-report.md) -> overall quality assessment and recommendations


## 📌 What This Project Demonstrates
- Test planning & strategy (risk-based approach)
- Reverse-engineered requirement analysis with acceptance criteria and full requirement-to-defect traceability (RTM)
- Feature-wise manual test suite design (80 test cases across 8 suites) covering positive, negative & edge-case scenarios
- Smoke Test Suite design
- Test Execution
- Defect reporting
- Test Summarization

## 📂 Repository Structure1

```
saucedemo-manual-testing/
├── 01-test-plan/
│   └── test-plan.md
├── 02-requirements-analysis/
│   └── requirement-analysis.md
├── 03-test-suites/
│   └── (8 feature-wise test suites)
├── 04-smoke-testing/
│   └── smoke-test-suite.md
├── 05-bug-reports/
│   └── (18 individual defect reports + index)
├── 06-screenshots/
│   └── (supporting evidence per defect)
├── 07-requirement-traceability/
│   └── rtm.md
├── 08-reports/
│   ├── test-execution-report.md
│   └── test-summary-report.md
└── README.md
```

📂 Repository Structure2

```
saucedemo-manual-testing/
│
├── 01-test-plan/
│   └── test-plan.md
│
├── 02-requirements-analysis/
│   └── requirement-analysis.md
│
├── 03-test-suites/
│   ├── authentication-login.md
│   ├── product-inventory.md
│   ├── product-detail.md
│   ├── shopping-cart.md
│   ├── checkout-step-one.md
│   ├── checkout-step-two.md
│   ├── checkout-complete.md
│   └── logout-session.md
│
├── 04-smoke-testing/
│   └── smoke-test-suite.md
│
├── 05-bug-reports/
│   ├── BUG-001.md
│   ├── BUG-002.md
│   └── ...
│
├── 07-requirement-traceability/
│   └── rtm.md
│
├── 08-reports/
│   ├── test-execution-report.md
│   └── test-summary-report.md
│
└── README.md
```
📂 Repository Structure3
```
saucedemo-manual-testing/
├── 01-test-plan
│   └── test-plan.md
├── 02-requirements-analysis
│   └── requirement.analysis.md
├── 03-test-suites
│   ├── ts00-authentication-login.md
│   ├── ts01-product-inventory.md
│   ├── ts02-product-detail.md
│   ├── ts03-shopping-cart.md
│   ├── ts04-checkout-stepone-customerinfo.md
│   ├── ts05-checkout-steptwo-overview.md
│   ├── ts06-checkout-stepthree-complete.md
│   └── ts07-logout-sessionhandling.md
├── 04-smoke-testing
│   └── smoke-test-suite.md
├── 05-bug-reports
│   ├── bug-001-page-loading-delay.md
│   ├── bug-002-incorrect-product-image-inventory.md
│   ├── ...
│   ├── bug-017-cross-user-cart-data-isolation.md
│   └── bug-018-about-link-404.md
├── 06-screenshots
├── 07-requirement-traceability
│   └── requirements-traceability-matrix.md
├── 08-reports
│   ├── test-execution-report.md
│   └── test-summary-report.md
└── README.md
```

## ⭐ QA Highlights

* 80 test cases executed across 8 different [test suites](03-test-suites).
* 22 failures investigated, re-tested to rule out false positives, and consolidated into 18 unique defects.
* Excluded 4 planned scenarios (e.g., username/password whitespace and casing checks) with no defined requirement to test against, rather than testing against assumptions.
* Designed [Smoke test-suite](04-smoke-testing/smoke-test-suite.md) covering the critical user journey (login → checkout → confirmation), traceable back to the full suite.
* Applied severity/priority based on actual user impact, not just pass/fail count.
* Documented downstream impact when defects affected later stages of the workflow, e.g., an unresponsive form field was traced through to the checkout-blocking failure it caused.
* Maintained full requirement-to-defect traceability via a dedicated [Requirement Traceability Matrix](07-requirement-traceability/requirements-traceability-matrix.md), rather than treating defects as standalone findings.
* Produced separate [Test Execution Report](08-reports/test-execution-report.md) and [Test Summary Report](08-reports/test-summary-report.md), distinguishing suite-by-suite results from overall quality assessment and release readiness.

## 🛠 Tools & Environment

* Tools & Technologies: Chrome (latest), Linux, Markdown, Git/GitHub, Playwright/TypeScript*(planned for automation)*
* AI Assistance: used for brainstorming and refining documentation
  
## 👤 Author
  Ananya Biswas · [LinkedIn](https://www.linkedin.com/in/ananya--biswas/) · [Portfolio](#)
