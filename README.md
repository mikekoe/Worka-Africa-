
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

### Prerequisites

- Git
- Node.js (LTS version) and npm
- A modern browser (Chrome, Firefox, Safari, or Edge)
- Postman (for running API collections manually)

### Setup

1. Clone the repository using SSH (ssh keys must have been added to github repo settings before this step)

       git clone git@github.com:mikekoe/Worka-Africa-.git

2. Move into the project folder

       cd worka-africa-qa-

3. Install dependencies

       npm install

4. Install Playwright browsers

       npx playwright install

5. Create your environment file from the template

       cp .env.example .env

6. Fill in `.env` with your own test values

       BASE_URL=https://workaafrica.com
       TEST_USER_EMAIL=<your test account email>
       TEST_USER_PASSWORD=<your test account password>

7. Create a working branch from `main`

       git switch -c feature/<area>

### Running Tests

- Run all UI tests

      npx playwright test

- Run a single test file

      npx playwright test tests/e2e/login.spec.js

- Run tests in a specific browser

      npx playwright test --project=firefox

- Run tests with the browser visible

      npx playwright test --headed

- Open the HTML test report

      npx playwright show-report

- Run API tests with Newman

      npx newman run tests/api/worka-api.postman_collection.json

## Branching
| Branch | Purpose |
|---|---|
| `main` | Stable, reviewed work only. No direct commits. |
| `feature/planning` | Test plan, feature inventory, bug report template |
| `feature/exploratory` | Test plan, Test case, and bugs documentation |
| `feature/automation` | API tests and UI automation scripts |
| `feature/completion` | Test review, and test completion documentation |


## Deliverables

- Test plan and test case documentation
- Automated test suites
- Bug reports with severity and priority
- Test summary report

## Author
Michael Adeyeye - QA Engineer 


