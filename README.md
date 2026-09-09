# SauceDemo Manual Testing Project

A manual QA portfolio project testing the [SauceDemo](https://www.saucedemo.com) e-commerce app end-to-end; covering functional, negative, UI, and user-specific test scenarios.

This repository contains the test cases, execution results, defect documentation, and supporting evidence created while testing the application's main user workflows.

**72.5% pass rate (58/80 passed) · 18 defects logged · 13 rated Critical/High severity**

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
* Removed scenarios where expected behavior could not be justified by a requirement.
* Consolidated duplicate observations into single defects.
* Applied severity/priority based on actual user impact.
* Documented downstream impact when defects affected later stages of the workflow.
