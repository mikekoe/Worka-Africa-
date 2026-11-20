
# Worka Africa QA Suite

Quality assurance project for [Worka Africa](https://workaafrica.com), an AI-powered jobs marketplace that connects employers in Africa with talent across the diaspora. This repo holds the test plan, test cases, automation scripts, and bug reports for the platform.

## Scope

**Candidate features**
- Registration, login, and profile setup
- Job browsing and AI semantic job search
- AI CV generator and cover letter writer
- ATS score checker
- Auto-apply
- Portfolio builder
- Salary insights and skills gap analyzer
- Interview prep

**Employer features**
- Job posting and management
- AI-ranked applicant matching

**Site-wide**
- Navigation, pricing, blog, and footer links
- Responsive layout and cross-browser behavior
- Performance, accessibility, and basic security checks

## Test Types

- Functional and manual exploratory 
- End-to-end Regression testing (Playwright) 
- UI/UX and responsive testing
- API testing (Postman)
- Cross-browser and cross-device testing
- CI/CD Pipeline Testing and Validation
- Accessibility Testing (WCAG) compliance (axe devtools)
- Performance testing(Apache Jmeter)


## Tech Stack

- Playwright for E2E automation
- Postman for API tests
- Jmeter and axe devtools for performance and accessibility
- GitHub Actions for CI

## Repo Structure

    ├── docs/            # Test plan,  bug report, test-summary
    ├── tests/
    │   ├── e2e/         # UI automation
    │   └── api/         # API tests
    ├── bug-reports/     # Logged defects with steps and screenshots
    └── README.md

## Getting Started

    git clone https://github.com/<your-username>/worka-africa-qa-suite.git
    cd worka-africa-qa-
    npm install
    npx playwright test

## Deliverables

- Test plan and test case documentation
- Automated test suites
- Bug reports with severity and priority
- Test summary report

## Author
Michael Adeyeye - QA Engineer 


