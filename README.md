# SauceDemo Manual Testing Project

A manual QA portfolio project demonstrating the end-to-end testing of the SauceDemo e-commerce application; including functional, negative, UI, and user-specific test scenarios.
The project simulates a structured software testing process covering test planning, requirement analysis, test design, smoke testing, test execution, defect reporting, traceability, and test summarization.

**Test Results at a glance:** 72.5% pass rate (58/80 passed) · 18 defects logged · 13 rated Critical/High severity

## 🖥️ Application Under Test

Application: SauceDemo

Website: https://www.saucedemo.com/

Type: Demo e-commerce web application



## 📑 Explore the Project

- [Test Plan](01-test-plan/test-plan.md) -> scope, approach, and strategy
- [Requirement Analysis](02-requirements-analysis/requirement-analysis.md) -> reverse-engineered functional requirements
- [Test Suites](03-test-suites/) -> 80 test cases across 8 feature suites
- [Smoke Test Suite](04-smoke-testing/smoke-test-suite.md) -> 11-case critical-path suite
- [Defect Reports](05-bug-reports/) -> 18 individual bug reports
- [Requirement Traceability Matrix](07-requirement-traceability/rtm.md) -> requirement ↔ test case ↔ defect mapping
- [Test Execution Report](08-reports/test-execution-report.md) -> full results, findings, and defect analysis
- [Test Summary Report](08-reports/test-summary-report.md) -> overall quality assessment and recommendations


## 📌 What This Project Demonstrates
- Test planning & strategy (risk-based approach)
- Reverse-engineered requirement analysis with acceptance criteria and full requirement-to-defect traceability (RTM)
- Feature-wise manual test suite design (80 test cases across 8 suites) covering positive, negative & edge-case scenarios
- Smoke testing
- Test Execution
- Defect reporting
- Test Summarization
- Test automation with Playwright/TypeScript *(planned)*

## 📂 Repository Structure

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

## ⭐ QA Highlights

* 80 test cases executed across authentication, inventory, cart, product detail, checkout, and session management.
* 22 failures investigated and consolidated into 18 unique defects.
* Re-tested unexpected behavior before reporting defects to avoid false positives.
* Removed 4 planned scenarios (e.g., username/password whitespace and casing checks) where expected behavior could not be justified by a requirement.
* Consolidated duplicate observations into single defects, e.g., the same `problem_user` product-image mismatch found on 4 separate pages was tracked as one defect (BUG-007), not four.
* Applied severity/priority based on actual user impact, not just pass/fail count.
* Documented downstream impact when defects affected later stages of the workflow, e.g., an unresponsive form field was traced through to the checkout-blocking failure it caused.

## 🛠 Tools & Environment
  Manual testing · Chrome (latest) · Linux · Markdown · GitHub-based defect documentation · Playwright/TypeScript *(planned for automation)*

## 👤 Author
  Ananya Biswas — [LinkedIn](#) · [Portfolio](#)
