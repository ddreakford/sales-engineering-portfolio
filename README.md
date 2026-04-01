# Sales Engineering Portfolio

**Dwayne Dreakford** | Sales Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/dwaynedreakford/)
[![GitHub](https://img.shields.io/badge/GitHub-ddreakford-333?style=flat&logo=github)](https://github.com/ddreakford)

---

## What You'll Find Here

This portfolio connects technical projects to the business outcomes they enable. It's indicative of how I approach the technical seller's role within the wider context of the sales cycle: 

- **Understand the domain and challenges** to maximizing business value
- **Identify key requirements and practical value** of addressing the challenges
- **Clarify how you, in differentiated fashion, provide a solution** that meets the requirements
- **Prove the viability of the business case** as it pertains to the solution to be provided

The projects below were built to make SEs more effective in clarifying the practical value and proving the viability of the business case.

Few things inspire confidence like tangeable examples.

---

## Projects

### Containerized Appium Testing Environment
**Repo:** [CommunityCode-AppiumCodeExamples](https://github.com/ddreakford/CommunityCode-AppiumCodeExamples) · [SE Perspective](https://github.com/ddreakford/CommunityCode-AppiumCodeExamples/blob/master/SE-README.md) · [Technical README](https://github.com/ddreakford/CommunityCode-AppiumCodeExamples/blob/master/README.md)

A reusable, containerized testing environment to simplify running tests on mobile devices in the Digital.ai Testing Cloud. Built to eliminate the days of setup that SEs typically burn before they can demonstrate platform value.

- **30+ ready-to-run scenarios** covering basic through advanced capabilities (Android & iOS)
- **Containerized execution** (Docker/Docker Compose) — consistent environments, no local dependency headaches
- **Two-level parallel execution** for demonstrating enterprise-scale throughput
- **Integrated accessibility scanning** (axe DevTools / WCAG) and **performance instrumentation** (CPU, battery, memory, network)
- **Self-healing test capabilities** — tests adapt automatically when UI elements change between app versions

**SE Impact:** Reduced demo and POC setup from days to hours. Enabled multi-persona engagement across QA leads, engineering managers and compliance leaders in a single evaluation.

**Case Study:** [Testing Environment Impact](case-studies/testing-environment-impact.md)

**Tech:** Java, Python, Appium, TestNG, pytest, Gradle, Docker, Digital.ai Testing Cloud

---

### Multi Test Type Demo Sandbox
**Repo:** [test-automation-demo](https://github.com/ddreakford/test-automation-demo) · [Setup Guide](https://github.com/ddreakford/test-automation-demo/blob/main/docs/TestAutomationDemo_SetupGuide.md) · [Technical README](https://github.com/ddreakford/test-automation-demo/blob/main/README.md)

Automated and manual tests targeting a hotel booking system. Automated and manual tests are included to validate the target system UI and API. Consumable reporting is provided via Allure Framework. Instructions and examples are provided for local setup as well plugging the automated tests into a CI pipeline.

- **23 automated tests** spanning API (via **RestAssured**) and UI (via **Selenium WebDriver**) layers, organized into auth, CRUD and functional regression suites
- **Allure reporting** with rich dashboards, step-level detail and historical trend tracking
- **Root cause analysis** — two intentional test failures illustrate RCA methodology using the Allure dashboard
- **Manual testing tutorial** with step-by-step scenarios and Selenium-captured reference screenshots for manual testers
- **GitHub Actions CI** — every push runs the full suite, executes the RCA demo and makes the Allure report available as a downloadable artifact

**SE Impact:** Provides a ready-made, end-to-end reference implementation to explore and  demonstrate multiple types and aspects of testing, including API contract validation, UI regression, manual testing, reporting and CI integration — in a cloneable, containerized setup.

**Case Study:** [Multi Test Type Demo Sandbox](case-studies/test-automation-demo-impact.md)

**Tech:** Java, Gradle, RestAssured, Selenium WebDriver, TestNG, Allure Report, Docker, GitHub Actions

---

### Mobile Application Security Assessment Framework
**Repo:** `mobile-app-assessment` [***unavailable / removed***]

A toolkit to conduct mobile security assessments aligned to OWASP MASVS v2.0. Built to enable SEs who are not security SMEs to facilitate credible security conversations with CISOs and application security teams.

- **Complete assessment workflow** — decompilation, vulnerability hunting, MASVS-RESILIENCE analysis, professional reporting
- **AI-assisted workflow** reduces evaluations from 8-12 hours to 4-6 hours
- **CVSS v3.1 scoring** with professional report templates meeting enterprise governance expectations
- **Comparative analysis** tracks remediation effectiveness across app versions
- **Multi-audience deliverables** — technical reports, executive summaries, stakeholder email templates

**SE Impact:** Packaged security expertise into a repeatable process. Enabled security-focused discovery conversations that uncovered requirements often missed, and differentiated in technical evaluations through demonstrated "before and after remediation" comparison.

**Case Study:** [Security Assessment Framework](case-studies/security-assessment-framework.md)

**Tech:** JADX, APKTool, Python, Bash, OWASP MASVS v2.0, CVSS v3.1, Claude Code

---

## How I Think About Sales Engineering

I approach every technical investment through a lense of sales impact and force multiplication:

- **How will this facilitate selling conversations?** *Security assessment opened doors* with CISOs, security teams and developers. *Containerized testing environment highlighted the power and practical utility* of an enterprise grade, hosted test lab. *Multi test type demo sandbox provides a concrete reference implementation* that shows how various test types and focuses can be used in combination as part of a mature testing practice.
- **Will this shorten deal cycles?** If SEs spend less time on setup and more time on the customer conversation, deal velocity can be increased. The more expertise and best practice can be codified, the less bottlenecks we'll experience in scheduling and getting back to customers.
- **Will this improve win rates?** Full featured, use case oriented  demos and low-friction evaluations make a measurable difference.
- **Will this scale beyond me?** Community code, tutorials and containerized environments enable other SEs to benefit without needing to understand every implementation detail.

---

## Skills Overview

A detailed mapping of technical and business skills to the projects that demonstrate them is available in the [Skills Matrix](skills-matrix.md).

| Domain | Capabilities |
|--------|-------------|
| **Test Automation** | Appium 2.0+, Selenium WebDriver, RestAssured, TestNG, pytest, parallel execution, self-healing, accessibility (axe DevTools), performance instrumentation |
| **Mobile Security** | OWASP MASVS v2.0, CVSS v3.1, decompilation & static analysis, vulnerability identification, remediation roadmaps |
| **Infrastructure** | Docker, Docker Compose, GitHub Actions CI/CD, containerized test environments |
| **Test Reporting & RCA** | Allure Report dashboards, root cause analysis methodology, manual-to-automated test documentation |
| **Languages** | Java, Python, Bash, Gradle |
| **Sales Engineering** | POC/POT planning & delivery, multi-persona engagement, competitive differentiation, technical discovery, stakeholder communication |
| **Leadership** | Framework design for team reuse, SE onboarding, community code contribution, cross-functional collaboration (Product, CS, Sales) |

---

## Portfolio Structure

```
sales-engineering-portfolio/
├── README.md                  ← You are here
├── case-studies/
│   ├── testing-environment-impact.md
│   ├── test-automation-demo-impact.md
│   ├── security-assessment-framework.md
│   └── template.md
├── artifacts/
│   ├── diagrams/
│   └── screenshots/
├── skills-matrix.md
└── impact-statements.md
```

---

## Get in Touch

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/dwaynedreakford/) &nbsp; 
[![GitHub](https://img.shields.io/badge/GitHub-ddreakford-333?style=flat&logo=github)](https://github.com/ddreakford)

---

*This portfolio is a living document — updated as new projects and case studies are developed.*
