# Case Study: Full-Stack Test Automation Demo

## Executive Summary

Prospects evaluating test automation platforms often struggle to envision what a mature, well-structured test automation practice looks like across the full testing stack. I built a multi-service test automation framework — covering API testing, UI testing, professional reporting and CI/CD — against a Docker-based hotel booking application. The project serves as a concrete, end-to-end reference implementation that SEs can walk through during evaluations to show how the pieces fit together, from API contract validation through UI regression to Allure dashboards and GitHub Actions pipelines.

---

## Context

Selling test automation platforms and services requires more than describing features. Prospects — especially QA leads and engineering managers evaluating solutions — want to see how automated testing works in practice across their stack. They want to understand how API and UI tests coexist, how results are reported, how failures are investigated, and how everything ties into CI/CD.

The challenge is that most demo environments show isolated capabilities: an API test here, a UI test there, a screenshot of a report. Prospects are left to assemble the full picture in their heads. For teams early in their test automation journey, this gap between "feature demo" and "what our practice would look like" can stall evaluation progress.

---

## Challenge

Several gaps made it harder to deliver compelling, holistic test automation evaluations:

- **No end-to-end reference.** Demos typically showcased individual capabilities in isolation. Prospects couldn't see how API tests, UI tests, reporting and CI fit together in a single, working project.
- **Root cause analysis wasn't demonstrated.** When tests fail (and they will), the ability to quickly diagnose *why* is critical. Without an RCA walkthrough, prospects couldn't evaluate the debugging experience.
- **Manual testers were left out.** Many prospect teams include manual testers transitioning to automation. Without manual test documentation alongside automated tests, demos didn't speak to this audience.

---

## Technical Solution

I built a multi-service test automation framework targeting the Restful-Booker Platform — a Docker-based hotel booking application with REST APIs and a web UI — that demonstrates the full testing stack in a single project.

**Architecture:**

- **System under test:** Restful-Booker Platform (multi-service Docker Compose application) included as a Git submodule for self-contained reproducibility
- **API test layer:** RestAssured + TestNG covering authentication (cookie-based auth tokens) and booking CRUD operations (create, read, delete)
- **UI test layer:** Selenium WebDriver + TestNG covering admin login, homepage validation, end-to-end booking flow and contact form submission
- **Reporting:** Allure Report integration providing dashboards, step-level detail, screenshot attachments and historical trend tracking
- **CI/CD:** GitHub Actions pipeline that starts the SUT, runs all tests, executes the RCA demo and uploads the Allure report as a downloadable artifact

**Test Organization:**

| Suite | Tests | Coverage |
|-------|-------|----------|
| API Tests (Auth, Booking CRUD) | 5 | Cookie-based auth, create/read/delete bookings via REST |
| UI Test (Admin Login) | 1 | Browser-based admin panel login with Selenium |
| Regression Suite (Homepage, Booking Flow, Contact Form) | 17 | Full customer-facing UI validation |
| RCA Demo (intentional failures) | 2 | Root cause analysis methodology demonstration |

**RCA Demo:**

Two tests are intentionally designed to fail — one API test asserting the wrong status code, one UI test asserting the wrong page title. Both are *test defects, not system defects*. This distinction is the teaching point: the RCA demo walks through how to use Allure's dashboard to identify, classify and document failures — a skill that prospects need and rarely see demonstrated.

**Manual Test Tutorial:**

Three step-by-step manual test scenarios with Selenium-captured reference screenshots provide documentation for manual testers. The scenarios map 1:1 to the automated regression suite, showing the relationship between manual and automated approaches.

**Key Decisions:**

- **Multi-service SUT.** Using a Docker-based application with REST APIs and a web UI (rather than mock endpoints) ensures the demo reflects real-world testing complexity. Prospects see tests running against actual services.
- **Allure as the reporting layer.** Allure provides the kind of professional, interactive reporting that engineering managers and QA leads expect. Step-level detail, screenshot attachments and dashboard views make test results accessible to both technical and non-technical stakeholders.
- **Intentional failures for RCA.** Including tests that are *designed to fail* is a deliberate teaching tool. It demonstrates that test failure investigation is a first-class concern, not an afterthought.
- **Manual + automated side by side.** Including manual test scenarios alongside their automated equivalents speaks to teams in transition and demonstrates the automation value proposition concretely.

**Repo:** [test-automation-demo](https://github.com/ddreakford/test-automation-demo)

---

## Implementation

**Tools & Frameworks:**
- Java 17+ (JDK 21 for Gradle 8.14), Gradle (Groovy DSL)
- RestAssured (API testing)
- Selenium WebDriver (UI testing)
- TestNG (test organization and execution)
- Allure Report (reporting and dashboards)
- Docker, Docker Compose (SUT orchestration)
- GitHub Actions (CI/CD pipeline)
- Google Chrome (browser automation)

**Documentation:**
- Setup Guide with full architecture walkthrough, source code explanation, Allure report guide and RCA demo instructions
- Manual Test Tutorial with step-by-step scenarios and reference screenshots
- DOCX conversion script for sharing documentation with non-technical stakeholders

**Making it accessible:**
- Single `git clone --recurse-submodules` followed by `docker compose up` and `./gradlew clean test` gets the full environment running
- JDK setup guidance for macOS, Linux and Windows with multiple configuration options
- Clear separation between the main test suite (23 passing tests) and the RCA demo (intentional failures) so they don't interfere with each other

---

## Business Impact

- **End-to-end reference implementation for evaluations.** SEs can walk prospects through a complete, working test automation project that covers API, UI, reporting and CI — showing how the pieces fit together rather than describing them in isolation.
- **Professional reporting demonstrates maturity.** Allure dashboards with step-level detail, screenshots and trend tracking show prospects what test reporting looks like in a mature practice — a significant step up from console output or basic pass/fail summaries.
- **RCA demo addresses a real prospect concern.** Walking through root cause analysis on intentional failures demonstrates the debugging experience — something prospects care deeply about but rarely see in evaluations.
- **Manual test documentation enables multi-audience engagement.** Including manual test scenarios alongside automated tests speaks to manual testers in transition, QA leads evaluating automation strategy and engineering managers assessing team readiness.
- **CI pipeline shows production readiness.** The GitHub Actions integration demonstrates that automated testing isn't just a local development activity — it's part of the delivery pipeline. This addresses questions about CI/CD integration that arise in nearly every evaluation.

---

## Lessons Learned

- **A realistically architected SUT makes the demo credible.** Testing against a Docker-based, multi-service application — rather than mocked endpoints — produces a demo that feels authentic. Prospects can see the tests interacting with realistic services, which builds confidence.
- **Intentional failures are a powerful teaching tool.** The RCA demo consistently generates engaged conversation. Showing *how* to investigate failures — not just how to run passing tests — addresses a gap that most evaluations leave open.
- **Manual + automated tells a transition story.** Many teams are moving from manual to automated testing. Showing manual test scenarios alongside their automated equivalents makes the automation value proposition concrete and relatable.
- **Documentation is part of the deliverable.** The setup guide, manual test tutorial and DOCX export capability make this project usable beyond live demos. Prospects can share documentation internally, which extends the evaluation's reach within the buying committee.

---

*[Back to portfolio](../README.md)*
