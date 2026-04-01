# Case Study: Multi Test Type Demo Sandbox

## Executive Summary

Given a particular testing solution, in can be challenging to envision how, in practice, various testing types and techniques are facilitated to provide practical value. With the practical value clarified, a viable business case can be constructed and ROI measured. This project serves as an adaptable reference implementation of automated and manual testing of a hotel booking system. The test types/focuses include UI, API, automated and manual tests. The automated tests are runnable locally via CLI and via GitHub Actions to demonstrate CI integration.

---

## Context

Prospective customers — *especially QA leads and engineering managers* — want to clarify how  testing solutions will work in practice. Depending on "where a team is", testing practice maturity wise, it's super valuable to help them envision how the various test types and emphases come together in context of their delivery processes. Of particular importance are how results are reported, failures investigated and root-cause analysis facilitated, as these are where most team members reap the value on daily basis.

---

## Challenge

The challenge that motivated creation of this repo is that many testing demo setups are intended to showcase isolated capabilities: an API test here, a UI test there, a manual test writeup stored separately in some "team docs repo". If automation code is provided, it's up to the adopter to bridge the gap from CLI to CI pluggability... These gaps between "feature demos" and "what our practice would look like" can stall evaluation progress and value realization (**not to mention consume way too many SE cycles that could be spent engaging with customers**).

Several gaps make it harder to conduct compelling, holistic testing solution evaluations:

- **No end-to-end reference.** Demos, by design typically showcase individual capabilities in isolation. It's *really* helpful see how API tests, UI tests, reporting, local execution and CI fit together in a single, working project.
- **Root cause analysis (RCA) is under-represented.** When tests fail (and they will), the ability to quickly diagnose *why* is critical. It may be more valuable to demonstrate how a testing solution facilates RCA than it is show how to run tests! 
- **The relationship and comparative utility of manual tests is often left out.** Many teams include manual testers, many of whom are transitioning to automation. Without manual tests that can be clearly related to automated tests, transitioning teams are left to go elsewhere for assistance in making this connection.

---

## Technical Solution

This repo provides automated and manual test scripts to facilitate exploration and demonstration of all of the above types and emphases of tests. The tests target a multi-service hotel booking system that is deployed via Docker and Docker Compose. Automated and manual tests are provided that target the UI as well as APIs of the booking system.

**Architecture:**

- **System under test:** Restful-Booker Platform (multi-service Docker Compose application) included as a Git submodule for self-contained reproducibility
- **API test layer:** RestAssured + TestNG covering authentication (cookie-based auth tokens) and booking CRUD operations (create, read, delete)
- **UI test layer:** Selenium WebDriver + TestNG covering admin login, homepage validation, end-to-end booking flow and contact form submission
- **Reporting:** Allure Report integration providing dashboards, step-level detail, screenshot attachments and historical trend tracking
- **CI/CD:** GitHub Actions pipeline that starts the SUT, runs all tests, executes the RCA demo and uploads an Allure report as a downloadable artifact

**Automated Tests:**

| Suite | Tests | Coverage |
|-------|-------|----------|
| API Tests (Auth, Booking CRUD) | 5 | Cookie-based auth, create/read/delete bookings via REST |
| UI Test (Admin Login) | 1 | Browser-based admin panel login with Selenium |
| Regression Suite (Homepage, Booking Flow, Contact Form) | 17 | Full customer-facing UI validation |
| RCA Demo (intentional failures) | 2 | Root cause analysis methodology demonstration |

**RCA Demo:**

Two tests are intentionally designed to fail — one API test asserting the wrong status code, one UI test asserting the wrong page title. Both are *test defects, not system defects*. This distinction is the teaching point: the RCA demo walks through how to use Allure's dashboard to identify, classify and document failures.

**Manual Test Tutorial:**

Three step-by-step manual test scenarios with Selenium-captured reference screenshots provide documentation for manual testers. The scenarios map 1:1 to the automated regression suite, showing the relationship between manual and automated approaches.

**Key Decisions:**

- **Multi-service SUT.** Testing against a multi-service application with REST APIs and a web UI (rather than mock endpoints) provides insight to real-world testing complexity. Since the SUT is deployable via Docker / Docker Compose, the Quality Engineer can focus on testing.
- **Allure as the reporting layer.** Allure provides clear, interactive reporting that is expected by Quality Engineers and Managers, and is readily related to other testing / quality solutions. Step-level detail, screenshot attachments and dashboard views make test results accessible to both technical and non-technical stakeholders.
- **Intentional failures for RCA.** Tests that are *designed to fail* are included as a deliberate teaching tool. It demonstrates that test failure investigation is a first-class concern, not an afterthought.
- **Manual + automated, side by side.** Including manual test scenarios alongside their automated equivalents speaks to teams in transition and tangeably demonstrates the automation value proposition.

**Repo:** [multi-test-type-demo](https://github.com/ddreakford/multi-test-type-demo)

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
- Setup Guide with full architecture walkthrough, test code explanation, Allure report guide and RCA demo instructions
- Manual Test Tutorial with step-by-step scenarios and reference screenshots
- DOCX conversion script for sharing documentation with non-technical stakeholders

**Making it accessible:**
- To get the full environment up and running, `git clone --recurse-submodules`, followed by `docker compose up` and `./gradlew clean test`
- JDK setup guidance for macOS, Linux and Windows with multiple configuration options
- Clear separation between the main automated test suite (23 passing tests) and the RCA demo suite (which results in intentional failures) so they don't interfere with each other

---

## Business Impact (from SE perspective)

- **End-to-end reference implementation for evaluations.** A complete, working test automation project that covers API, UI, reporting and CI integration shows how these aspects fit together. This is big improvement over describing them in isolation.
- **Professional reporting helps to communicate the practical value.** Allure dashboards with use case / scenario grouping, step-level detail, screenshots and trend tracking are indicative of test reporting in a mature practice.
- **RCA demo addresses a real prospect concern.** Walking through root cause analysis on intentional failures demonstrates something prospects care deeply about but often don't see in evaluations.
- **Manual test documentation enables multi-audience engagement.** Including manual test scenarios alongside automated tests speaks to manual testers in transition, QA leads evaluating automation strategy and engineering managers assessing team readiness.
- **CI pipeline shows production readiness.** The GitHub Actions integration demonstrates the inclusion of automated testing in the delivery pipeline. This addresses questions about CI/CD integration that are raised in even the earliest conversations.

---

## Lessons Learned

- **A realistically architected SUT makes the demo credible.** Testing against a Docker-based, multi-service application — rather than mocked endpoints — produces a demo that feels authentic. Prospects can see the tests interacting with realistic services, which builds confidence.
- **Intentional failures are a powerful teaching tool.** The RCA demo consistently generates engaged conversation. Showing *how* to investigate failures — not just how to run passing tests — addresses a gap that most evaluations leave open.
- **Manual + automated tells a transition story.** Many teams are moving from manual to automated testing. Showing manual test scenarios alongside their automated equivalents makes the automation value proposition concrete and relatable.
- **Documentation is part of the deliverable.** The setup guide, manual test tutorial and DOCX export capability make this project usable beyond live demos. Prospects can share documentation internally, which extends the evaluation's reach within the buying committee.

---

*[Back to portfolio](../README.md)*
