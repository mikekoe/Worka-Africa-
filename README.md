# Work Africa End-to-End Web Application QA & AI/LLM Evaluation

Quality assurance project for [Worka Africa](https://workaafrica.com), an AI-powered jobs marketplace connecting employers in Africa with talent across the diaspora.

This repository contains test documentation, functional and AI/LLM evaluation test cases, Playwright automation scripts, API test collections, and defect reports. The project focuses on validating application functionality, user workflows, and the quality and reliability of AI-generated outputs.

## Scope

### Candidate Features
- User registration, login, and profile setup
- Job browsing and AI-powered semantic job search
- AI CV generator and cover letter writer
- ATS score checker
- Auto-apply functionality
- Portfolio builder
- Salary insights and skills gap analyzer
- Interview preparation

### Employer Features
- Job posting and management
- AI-powered applicant matching and ranking

### Site-wide Features
- Navigation, pricing, blog, and footer links
- Responsive layout and cross-browser behaviour
- Application performance and accessibility
- Basic security and input validation checks

*Feature availability will be verified during exploratory testing. Features that cannot be accessed or exercised within the project timeframe will be documented accordingly.*

## Test Types

- **Functional Testing:** Manual and exploratory testing of application features and user workflows.
- **End-to-End Regression Testing:** Playwright automation of critical user journeys.
- **UI/UX and Responsive Testing:** Validation of layouts, navigation, and usability across screen sizes.
- **API Testing:** Positive, negative, and boundary testing of accessible API endpoints using Postman.
- **Cross-browser Testing:** Verification of critical workflows across supported browsers.
- **AI/LLM Evaluation:** Basic black-box evaluation of AI-powered features using predefined prompts and expected behaviours.
- **Accessibility Testing:** Basic WCAG-oriented checks using axe DevTools.
- **Performance Testing:** Load and response-time checks using Apache JMeter.
- **CI Pipeline Validation:** Verification of automated test execution and reporting through GitHub Actions, where configured.

## AI/LLM Evaluation Approach

AI-powered features will be evaluated from an end-user perspective without accessing or modifying the underlying AI models.

The evaluation will focus on four areas:

| Evaluation Area | What is Being Tested |
|---|---|
| Semantic Relevance | Whether AI job search returns relevant results for exact keywords, related terms, and paraphrased queries. |
| Instruction Following | Whether generated CVs and cover letters follow the user's instructions and supplied information. |
| Hallucination Detection | Whether AI-generated content introduces fabricated qualifications, skills, experience, or other unsupported facts. |
| Output Consistency | Whether repeated prompts produce reasonably consistent and relevant outputs without changing important candidate information. |

### Evaluation Method
- Prepare a small set of predefined test prompts using fictional candidate information.
- Define expected behaviour for each prompt before execution.
- Submit prompts through the website's available AI features.
- Record actual responses and evaluate them against the expected behaviour.
- Use a simple 1–5 scoring scale to assess output quality.
- Document unexpected responses, inaccuracies, and potential AI-related defects.

**Scoring Criteria**

| Score | Description |
|---|---|
| 5 | Fully satisfies expectations. |
| 4 | Meets expectations with minor issues. |
| 3 | Partially satisfies expectations. |
| 2 | Has significant issues. |
| 1 | Fails to satisfy expectations. |

Evaluation results will be documented using Google Sheets and summarised in the project reports.

*This is a basic black-box evaluation exercise. No model training, custom AI frameworks, or specialised LLM evaluation platforms are required.*

## Tech Stack

| Tool | Purpose |
|---|---|
| Playwright | End-to-end UI automation and regression testing |
| TypeScript | Automation scripts and basic evaluation assertions |
| Postman | API testing and request validation |
| Newman | Command-line execution of Postman collections |
| Apache JMeter | Performance and load testing |
| axe DevTools | Accessibility testing |
| Google Sheets | AI evaluation dataset, scoring, and results |
| GitHub Actions | Test automation and CI pipeline execution |
| Git | Version control and collaboration |

## Repository Structure

```text
Worka-Africa-qa/
├── docs/
│   ├── test-plan.md
│   ├── test-summary-report.md
│   ├── ai-evaluation-report.md
│   └── bug-reports/
│   
├── tests/
│   ├── ui-e2e/
│   │   ├── authentication/
│   │   ├── job-search/
│   │   ├── candidate-profile/
│   │   └── ai-features/
│   
│   ├── api/
│   └── ai-evaluation/
│       └── evaluation-tests
│   
├── postman/
│   └── worka-api.postman_collection.json
│   
├── jmeter/
│   ├── reports/
│   ├── results/
│   └── worka-performance.jmx
│   
├── .github/
│   └── workflows/
│   
├── .env.example
├── package.json
├── playwright.config.ts
└── README.md
```

---

## Getting Started

### Prerequisites

Install the following tools:

- [Git](https://git-scm.com/)
- [Node.js (LTS)](https://nodejs.org/) and npm
- [Playwright](https://playwright.dev/)
- [Postman](https://www.postman.com/)
- [Newman](https://www.npmjs.com/package/newman) (for command-line API test execution)
- [Apache JMeter](https://jmeter.apache.org/) (for performance testing)
- [axe DevTools](https://www.deque.com/axe/devtools/) (for accessibility testing)
- A supported browser such as Chromium, Firefox, or WebKit

Google Sheets will be used for recording AI evaluation results. No additional LLM evaluation framework or AI API SDK is required.

### Installation References

- [Playwright Installation](https://playwright.dev/docs/intro)
- [Node.js Installation](https://nodejs.org/en/download)
- [Postman Documentation](https://learning.postman.com/)
- [Newman Documentation](https://learning.postman.com/docs/collections/using-newman-cli/command-line-integration-with-newman/)
- [JMeter Documentation](https://jmeter.apache.org/usermanual/get-started.html)
- [Java](https://www.java.com/en/download/manual.jsp)
- [axe DevTools](https://www.deque.com/axe/devtools/)

---
## Setup

### 1. Clone the Repository

```bash
git clone git@github.com:mikekoe/Worka-Africa-qa.git
```

### 2. Navigate to the Project Directory

```bash
cd Worka-Africa-qa
```

### 3. Configure Environment Variables

Create your local environment file:

```bash
cp .env.example .env
```

### 4. Update `.env` with your test environment details:

```env
BASE_URL=https://workaafrica.com
TEST_USER_EMAIL=<your-test-account-email>
TEST_USER_PASSWORD=<your-test-account-password>
```

## Running Tests

### Playwright

Generate Playwright tests
```bash
npx playwright test codegen
```

Run all UI tests:

```bash
npx playwright test
```

Run a specific test file:

```bash
npx playwright test tests/e2e/authentication/login.spec.ts
```

Run tests in headed mode:

```bash
npx playwright test --headed
```

View the HTML test report:

```bash
npx playwright show-report
```

---
### API Tests with Newman

Run a Postman collection:

```bash
npx newman run postman/worka-api.postman_collection.json
```

---
### JMeter

- Open JMeter GUI

```bash
jmeter
```

- Navigate to working directory

```bash
cd performance/jmeter
```

- Configure HTTP Request Defaults, HTTP Header Manager, User Defined Variables, HTTP methods

```bash
HTTP Configuration
Protocol: HTTP
Server: greenlife.localhost
Port: 8000
Authorization: token ${API_KEY}:${API_SECRET}
Accept: application/json
Content-Type: application/json
```

- Executing Jmeter in Non-GUI mode

```bash
jmeter -n \
  -t GreenLife_ERPNext_Performance_Test.jmx \
  -l results/stress/stress_test.jtl \
  -e \
  -o reports/stress_report
```

- Open the generated HTML report
```bash
open reports/stress_report/index.html
```

---
### AI/LLM Evaluation

AI evaluation will initially be performed through the website's accessible AI features.

1. Select a predefined evaluation prompt.
2. Submit it through the relevant AI feature.
3. Compare the generated response against the expected behaviour.
4. Assign a score using the evaluation criteria.
5. Record the actual output, observations, and any defects in the evaluation dataset.

Where appropriate, Playwright will automate prompt submission and capture generated responses. Human review will be used to assess relevance, accuracy, instruction following, and potential hallucinations.

## Deliverables

- Test plan and user stories document
- Functional and exploratory test cases
- Playwright end-to-end automation suite
- Postman API test collection and execution results
- AI/LLM evaluation dataset, criteria, and results
- Defect reports with reproduction steps, severity, and priority
- Performance and accessibility test results, where executed
- Test summary report

## Project Scope and Limitations

This QA project focused on practical testing of an AI-powered web application.

The AI evaluation is limited to observable application behaviour and generated outputs. It does not involve model development, training, fine-tuning, or internal model performance analysis.

Testing will prioritise critical user journeys, high-risk functionality, and accessible features. Any blocked, unavailable, or untestable functionality will be clearly documented rather than assumed to have passed.

## Author

**Michael Adeyeye**  
QA Engineer