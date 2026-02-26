# Case Study: Mobile Application Security Assessment Framework

## Executive Summary
Provision of a mobile application security assessment was already proving to be effective for demand generation, solution value selling and opportunity progression. Unfortunately, the time and effort required from a mobile security SME to perform the assessment led to a bottleneck. Promising opportunities remained in queue, awaiting assessment results that the sales team could use to move things forward. After taking a 201-level security assessment course and performing my first assessment, it became clear that I could do the job more thoroughly, consistently *and* faster by codifying the repeatable aspects. 

Over approximately a calendar month, I iteratively built an assessment framework aligned to OWASP MASVS v2.0 that packages methodology, tooling and professional-grade reporting into a repeatable process. The codified, phase-by-phase guidance enabled SEs who are not security SMEs to conduct credible assessments in 4-6 hours (down from 8-12), deliver CVSS-scored reports that meet enterprise governance expectations, and track remediation effectiveness across app versions. Beyond value as a demand generation and selling tool, the framework turns a one-time assessment into a compass for guiding ongoing customer engagement.

---

## Context

As a leading provider of application security solutions, conversations with prospects came with the expectation that we could help them understand their exposure, assess the extent to which our platform could support or enhance their security practices, and validate remediation efforts. CISOs, application security teams and application developers were typically involved.

The problem was that these conversations require specific expertise — familiarity with OWASP standards, vulnerability scoring, decompilation tools and the ability to translate findings into business-relevant remediation roadmaps. Most SE teams, including ours, don't have enough seasoned security SMEs to directly support the progression of every deal, especially at the earlier stages. Conversations (and opportunity progression) often needed to be deferred until an already overbooked specialist was available.

This situation elevated the risk of opportunity loss. There was also opportunity inherent in providing crystal clarification of prospective customers' exposure, while setting the stage to highlight the effectiveness and competitive differentiation of our solution.

---

## Challenge

Several gaps were limiting the team's ability to optimally progress security solution conversations:

- **Expertise bottleneck.** Security conversations depended on one or two specialists. When they weren't available, deals stalled or the security discussion was inadequately handled.
- **No standardized approach.** When assessments were conducted, each one was ad hoc — different tools, different depth, different reporting formats. This made it hard to deliver consistent quality or scale the capability.
- **Assessment time was prohibitive.** A thorough manual assessment could take 8-12 hours. In the context of a sales cycle, that's a significant investment to make on a prospect without a clear path, let alone a commitment, to purchase.
- **Findings without context.** Even when vulnerabilities were identified, presenting technical findings to non-technical stakeholders (CISOs, VP Engineering, compliance leads) required translation work that ate time in a fashion that didn't seem optimal.

---

## Technical Solution

I built an assessment framework that codifies the full methodology — from app decompilation through reporting — into a repeatable, documented process with templates, tooling and guides at each stage.

**Architecture:**

The framework is organized as an exemplar (template repository) with four elements:

1. **Analysis Guides** — step-by-step methodology for each assessment phase, plus deep-dive guides for all four OWASP MASVS-RESILIENCE controls (root detection, obfuscation, anti-debugging, tamper detection)
2. **Templates** — professional report templates (assessment report, comparative analysis, individual findings, MASVS controls mapping, stakeholder email summaries)
3. **Tools** — automation scripts for setup, decompilation, credential scanning, quick scanning and sanitization
4. **Workflow Documentation** — three assessment approaches (AI-assisted, manual, hybrid) with time estimates and guidance for when to use each

**Assessment Workflow:**

| Phase | Activity | Time (AI-assisted) |
|-------|----------|-------------------|
| 1 | Setup & Decompilation (JADX, APKTool) | 30-60 min |
| 2 | Initial Reconnaissance (manifest analysis, code structure) | 20-30 min |
| 3 | Vulnerability Hunting (credentials, configs, weak crypto) | 1-2 hours |
| 4 | MASVS-RESILIENCE Analysis (4 controls, scored 0-10) | 1-1.5 hours |
| 5 | Documentation & Reporting (CVSS scores, MASVS mapping, remediation) | 1-2 hours |
| 6 | Comparative Analysis (post-remediation tracking — optional) | 1-2 hours |

**MASVS-RESILIENCE Deep Dives:**

Each of the four RESILIENCE controls gets an enhanced guide (1,200-1,700 lines each) covering:
- AI-assisted and manual analysis approaches
- Implementation pattern recognition (7-8 variations per control)
- Scoring rubric (0-10 scale with clear criteria)
- Evidence documentation standards
- Comparative analysis methodology for re-assessment

**Reporting:**

- **Assessment Report** — executive summary, findings with CVSS v3.1 vector strings, impact analysis, attack scenarios, three-phase remediation roadmap (emergency / short-term / long-term)
- **Comparative Report** — side-by-side version comparison, remediation quality scoring, remaining gap identification
- **Stakeholder Communication** — email templates for different audiences, executive summaries that translate technical findings into business impact

**Key Decisions:**

- **Exemplar model, not a product.** The framework is a template repository. When you need to conduct an assessment, you create a new assessment from the template using `create_new_assessment.sh`. This keeps the exemplar clean and each assessment self-contained.
- **Three assessment approaches.** Rather than prescribing one methodology, the framework supports AI-assisted (fastest), manual (most thorough) and hybrid (recommended balance). SEs choose based on the engagement context and time available.
- **MASVS-RESILIENCE focus.** While the framework covers all 20 OWASP MASVS controls at a high level, the deep-dive guides focus on the four RESILIENCE controls. These are the controls most relevant to the conversations SEs were having — and the ones most likely to yield actionable, differentiating findings.
- **Built-in sanitization.** A sanitization script (`sanitize_guides.py`) and comprehensive `.gitignore` ensure that assessment artifacts (actual APKs, decompiled code, client-specific findings) never leak into the public template.

**Repo:** `mobile-app-assessment` [***unavailable / removed***]

---

## Implementation

**Tools & Standards:**
- JADX 1.5.0+ (dex-to-Java decompilation)
- APKTool 2.12+ (resource extraction, manifest parsing)
- Python, Bash (automation scripts)
- Claude Code (AI-assisted analysis, report generation)
- OWASP MASVS v2.0, CVSS v3.1, CWE, OWASP MSTG

**Building the methodology:**
- Studied OWASP MASVS v2.0 and MSTG to establish the standards foundation
- Conducted multiple assessments to validate timing estimates, identify common patterns and refine the scoring rubrics
- Iterated on the AI-assisted workflow to find the right balance between automation speed and human judgment (for example, AI is excellent at pattern matching and report drafting; but enforcement-vs-telemetry analysis and risk scoring require human validation)

**Making it accessible:**
- `GETTING_STARTED.md` provides a complete walkthrough for first-time assessors — from tool installation through report delivery
- The analysis guides are layered: beginners start with `GETTING_STARTED.md`, reference `ASSESSMENT_WORKFLOW.md` for the intermediate view, and dive into the enhanced MASVS guides only when they encounter findings that warrant deeper analysis
- Templates use `[PLACEHOLDER]` formatting throughout so assessors know exactly where to insert their findings without guessing at the report structure

---

## Business Impact

- **Security conversations no longer bottlenecked by specialist availability.** Most SEs with the framework can conduct a credible, OWASP-aligned assessment and deliver professional-grade reporting. This distributes the security conversation capability across the team.
- **Assessment time cut significantly.** The AI-assisted workflow reduced evaluations from 8-12 hours to 4-6 hours while maintaining comprehensive MASVS coverage. This makes it practical to offer assessments as part of the sales process rather than treating them as exceptional, resource-intensive engagements.
- **Discovery conversations uncovered requirements competitors missed.** Security-focused discovery — guided by the assessment methodology — surfaces requirements that weren't in the original evaluation criteria. This expands deal scope and positioned us as a partner who understands the prospect's broader challenges.
- **Trust-building through transparency.** Demonstrating a rigorous, documented methodology — and explaining *how* findings were identified and scored — built prospect confidence in a way that a slide deck about security features never could.
- **Post-assessment engagement.** The comparative analysis capability turns a one-time assessment into an ongoing relationship. After the prospect remediated findings, we could re-assess and demonstrate measurable improvement — reinforcing the business case and supporting expansion conversations.
- **Multi-audience communication.** Delivering technical reports to engineering teams, executive summaries to leadership and actionable remediation roadmaps aligned to business timelines meant that findings move through the organization instead of sitting in a PDF.

---

## Lessons Learned

- **Codified methodology scales; individual expertise doesn't.** The biggest impact wasn't my ability to conduct assessments — it was enabling other SEs to do it. The framework templates and guides turned a specialist skill into a team capability.
- **AI assistance is a multiplier, not a replacement.** Claude Code dramatically accelerated pattern matching, report drafting and CVSS calculation. But the judgment calls — enforcement vs. telemetry, actual exploitability, risk prioritization — require a human who understands the prospect's context. The hybrid approach is the right default.
- **The assessment itself is a sales tool.** Offering to assess a prospect's actual app — and delivering a professional report with actionable findings — creates immediate, tangible value. It shifts the conversation from "what can your platform do?" to "here's what we found, and here's how we can help you fix it."
- **RESILIENCE controls were the right focus.** Deep-diving on root detection, obfuscation, anti-debugging and tamper detection consistently produced the most relevant and differentiating findings. Broader MASVS coverage matters for completeness, but the RESILIENCE controls drove the most impactful conversations.

---

*[Back to portfolio](../README.md)*
