# GitHub-LinkedIn Portfolio Showcase Plan
**Goal:** Position for Sales Engineer roles by demonstrating technical depth + business impact

**Working Environment:** VS Code with Claude Code, Git for version control

---

## How This Plan Was Executed

This plan was executed collaboratively between Dwayne and Claude Code. The workflow that emerged — and that should be repeated for future additions — was:

1. **Claude drafts content** based on deep analysis of the actual repositories (code, docs, architecture)
2. **Dwayne reviews and edits** to adjust voice, tone, accuracy and business framing
3. **Claude incorporates the editorial direction** into subsequent content, progressively matching Dwayne's style

This iterative approach was particularly important for:

- **Impact statements** — Claude's initial draft was technically grounded but needed Dwayne's edits to capture the right SE perspective (e.g., reframing "test automation framework" as "containerized testing environment," emphasizing the distinction between providing containerization vs. writing all test scenarios, adding the personal voice and sales context)
- **SE-README.md content** — Claude drafted the Business Context / Why This Matters sections (initially added to project READMEs, later separated into dedicated `SE-README.md` files); Dwayne's edits sharpened the problem framing, adjusted use case descriptions and added personality (the "strain their sanity (lol)" note, for instance)
- **Case study narratives** — Claude drafted complete case studies using the template structure; Dwayne's edits added critical context (the security case study's executive summary was substantially rewritten to include the personal narrative of taking a 201-level course, the testing case study added the clarifying note about providing containerization on top of existing community code)

**Key editorial patterns Dwayne established:**

- **Frame problems in terms of sales impact** — not just "SEs had setup issues" but "this prework can eat up *days* worth of SE cycles and force technical sellers to compromise on what they can show or prove"
- **Distinguish contribution clearly** — when the work builds on existing assets, call that out explicitly (e.g., "I provided the containerized configuration/execution approach" vs. implying all code was written from scratch)
- **Use the language of the sales cycle** — deal velocity, opportunity progression, demand generation, business case viability — not generic "business impact"
- **Include the human element** — the voice should be direct and occasionally informal, not corporate-polished

**For future case studies and impact statements:** Have Claude draft based on repo analysis, then apply these editorial patterns during review. The template in `case-studies/template.md` provides the structure; the existing case studies provide the tone.

---

## Phase 1: Foundation & Setup ✅
**Objective:** Establish portfolio structure and prepare working environment

### Completed
- [x] Create new GitHub repository: `sales-engineering-portfolio`
  - Initialized with README.md and `.gitignore`
  - Set repository visibility to Public
  - Created via `gh repo create` with GitHub CLI
  - Remote: https://github.com/ddreakford/sales-engineering-portfolio

- [x] Review existing repos for confidentiality
  - [x] Audited `CommunityCode-AppiumCodeExamples` — **LOW RISK**, clean
    - All credentials use placeholders (`.env.example` pattern)
    - Only public vendor URLs and demo data
    - No client names, NDA-protected info or internal references
  - [x] Audited `mobile-app-assessment` — **LOW RISK**, clean
    - Template repository with empty placeholder directories
    - Built-in sanitization script and comprehensive `.gitignore`
    - All templates use `[PLACEHOLDER]` formatting
  - [x] Documented generalized impact statements (`impact-statements.md`)
    - Claude drafted initial statements from repo analysis
    - **Dwayne edited** to sharpen SE framing, adjust categorization and refine language
    - Final version organized by project with cross-project themes

- [x] Set up local Git workflow
  - VS Code Git integration configured
  - Commit/push workflow tested with initial commit
  - Working on `main` branch (feature branches available for future work)

**Deliverable:** Portfolio repository created + existing repos confirmed clean

---

## Phase 2: Enhance Existing Repositories with SE Content ✅
**Objective:** Add sales engineering context to project repositories

*Initially, SE sections were added directly to each project's README. Before launch (v1.1), these were separated into dedicated `SE-README.md` files so that project READMEs remain purely technical and SE content lives in its own document. Each README now includes a one-line pointer to its SE-README.md.*

### Repository 1: CommunityCode-AppiumCodeExamples ✅

- [x] Created SE content (now in `SE-README.md`)
  - "Business Context" with "Why This Exists" narrative + "Sales Engineering Value" bullets
  - Claude drafted; **Dwayne edited** problem framing, added emphasis on days of lost SE cycles, and refined the containerization value proposition
- [x] Created "Use Cases" section (now in `SE-README.md`)
  - 2 anonymized scenarios (Compelling Demo/Evaluation, Onboarding SEs)
  - Challenge → Solution → Outcome format
  - **Dwayne edited** to add personality and specificity (evaluation window timing, "strain their sanity (lol)")
- [x] Separated SE content into `SE-README.md`; restored README to technical-only with pointer
- [ ] Visual elements (architecture diagrams, screenshots) — deferred to future iteration

**Deliverable:** SE-README.md showing SE thinking + technical README focused on the code

### Repository 2: mobile-app-assessment ✅

- [x] Created SE content (now in `SE-README.md`)
  - "Why This Matters in Sales Engineering" — Problem/Solution/SE Value structure
  - **Dwayne edited** problem statement to frame from solution provider perspective
- [x] Created "How This Supports the Sales Cycle" table (now in `SE-README.md`)
  - Maps assessment value to each sales stage (Discovery → Post-Sale)
  - **Dwayne edited** to sharpen the value descriptions (e.g., "foundational input for the business case" in POC stage)
- [x] Created "Skills Demonstrated" table (now in `SE-README.md`)
  - **Dwayne edited** to add "Comprehensive examination" and reorder rows
- [x] Separated SE content into `SE-README.md`; restored README to technical-only with pointer
- [ ] Visual elements — deferred to future iteration

**Deliverable:** SE-README.md positioning security assessment as SE differentiator + technical README focused on the methodology

---

## Phase 3: Build Portfolio Repository ✅
**Objective:** Create central hub connecting LinkedIn experience to GitHub projects

### Portfolio Repository Structure

```
sales-engineering-portfolio/
├── README.md                  (Landing page)
├── case-studies/
│   ├── testing-environment-impact.md
│   ├── security-assessment-framework.md
│   └── template.md
├── artifacts/
│   ├── diagrams/
│   └── screenshots/
├── skills-matrix.md
├── impact-statements.md
└── portfolio-showcase-plan.md  (This file)
```

### Completed
- [x] Created compelling README.md (landing page)
  - Professional introduction with LinkedIn/GitHub badges
  - SE philosophy framework (understand domain → identify requirements → clarify solution → prove business case)
  - Project summaries with repo links, capability bullets, SE impact and case study links
  - "How I Think About Sales Engineering" section
  - Skills overview table with link to full matrix
  - Contact CTA
  - Claude drafted; **Dwayne substantially edited** the philosophy section, project descriptions, SE thinking framing and call-to-action voice

- [x] Created Skills Matrix (`skills-matrix.md`)
  - Technical Skills table (11 skills with proficiency, evidence, project links)
  - Business & SE Skills table (9 skills with evidence and project links)
  - Experience-to-Project Mapping table
  - Claude drafted; **Dwayne edited** proficiency levels, evidence descriptions and skill naming

- [x] Created case study template (`case-studies/template.md`)
  - 8-section structure: Executive Summary, Context, Challenge, Technical Solution, Implementation, Business Impact, Skills Demonstrated, Lessons Learned
  - Includes writing prompts for each section

**Deliverable:** Portfolio repository with landing page, skills matrix and template

---

## Phase 4: Create Narrative Content ✅
**Objective:** Write compelling case studies that showcase SE value

*Combined with Phase 3 execution — case studies written during portfolio build rather than as a separate phase.*

### Case Study Template Structure
Each case study follows this format:

1. **Executive Summary** (elevator pitch for the whole case study)
2. **Context** (what was happening in the sales/engagement environment)
3. **Challenge** (specific problems impacting sales effectiveness)
4. **Technical Solution** (architecture, key decisions, repo link)
5. **Implementation** (tools, collaboration, how it was made accessible)
6. **Business Impact** (generalized outcomes maintaining confidentiality)
7. **Lessons Learned** (what worked, what to do differently)

*Note: "Skills Demonstrated" section was removed from the case studies during editing — skills are covered in the skills matrix and README. Case studies focus on narrative.*

### Completed

- [x] Case Study 1: Testing Environment Impact (`testing-environment-impact.md`)
  - Claude drafted from deep repo analysis
  - **Dwayne substantially edited:**
    - Added clarifying note distinguishing containerization contribution from existing test scenario code
    - Updated repo links to point to upstream `dai-continuous-testing` organization
    - Refined Context section (platform was "plenty capable," challenge was "getting to the demo")
    - Adjusted Lessons Learned language ("audible ready" concept, emphasis on opportunity progression)

- [x] Case Study 2: Security Assessment Framework (`security-assessment-framework.md`)
  - Claude drafted from deep repo analysis
  - **Dwayne substantially rewrote Executive Summary** to include personal narrative (taking a 201-level course, recognizing the codification opportunity)
  - **Dwayne edited Context** to frame from solution provider perspective, emphasize opportunity loss risk
  - Adjusted Challenge descriptions and Business Impact language

- [x] Created case study template for future additions (`case-studies/template.md`)

**Deliverable:** 2 polished case studies + reusable template

---

## Phase 5: LinkedIn Integration
**Objective:** Connect LinkedIn profile to GitHub portfolio

### Tasks

- [ ] Update LinkedIn Profile Summary
  - [ ] Add link to portfolio repository in "About" section
  - [ ] Include 1-2 sentences highlighting technical + business capabilities
  - [ ] Reference specific frameworks/methodologies (with GitHub links)

- [ ] Enhance LinkedIn Experience Entries
  - [ ] Add GitHub repo links to relevant job experiences
  - [ ] Include brief mention of technical contributions

- [ ] Update LinkedIn Skills Section
  - [ ] Add/endorse technical skills visible in GitHub (Appium, TestNG, Docker)
  - [ ] Add/endorse SE skills (Solution Design, Technical Sales, POC Management)

- [ ] Consider LinkedIn Featured Section
  - [ ] Add portfolio repository as featured item
  - [ ] Add case study documents as featured items
  - [ ] Reorder to highlight most relevant content first

- [ ] Optional: LinkedIn Activity
  - [ ] Short post announcing portfolio launch
  - [ ] Highlight what hiring managers/recruiters will find

**Deliverable:** LinkedIn profile seamlessly directs to GitHub portfolio

---

## Phase 6: Review & Polish ✅
**Objective:** Ensure professional quality and consistency

### Completed

- [x] Technical accuracy review
  - [x] All external GitHub links verified (5 URLs, all return 200)
  - [x] All internal file links verified against actual directory contents
  - [x] Fixed broken case study link in README (`automation-framework-impact.md` → `testing-environment-impact.md`)
  - [x] Fixed duplicate word in impact-statements.md ("aligned aligned")
  - [x] Added `.gitkeep` files to empty artifact directories

- [x] Content review
  - [x] Confidentiality audit completed (Phase 1) — both repos clean
  - [x] Voice and tone established through iterative Claude draft → Dwayne edit workflow
  - [x] All client references anonymized

- [ ] Visual elements — deferred (architecture diagrams, screenshots)
- [ ] GitHub rendering test — to be done after commit/push

**Deliverable:** Publication-ready portfolio (pending visual elements)

---

## Phase 7: Launch & Iterate ✅ (partially)
**Objective:** Publish and maintain portfolio

### Completed

- [x] Commit and push all portfolio content
  - [x] Stage and commit portfolio files (9 files, 863 lines)
  - [x] Push to remote
  - [x] Tag release v1.0
  - [x] Update repository description and topics on GitHub

- [x] Add repository topics/tags
  - sales-engineering, test-automation, appium, mobile-testing, portfolio, security-assessment

- [x] Commit and push SE content to existing repos
  - [x] `CommunityCode-AppiumCodeExamples` — SE-README.md created, README restored to technical-only
  - [x] `mobile-app-assessment` — SE-README.md created, README restored to technical-only

- [x] Tag release v1.1 (SE-README separation)
  - [x] Portfolio README updated with SE Perspective + Technical README links per project
  - [x] All three repos committed and pushed

### Remaining

- [ ] Share portfolio
  - [ ] Update LinkedIn with all links (Phase 5)
  - [ ] Add portfolio link to resume
  - [ ] Share with trusted network for feedback

- [ ] Set maintenance schedule
  - [ ] Add new case studies as projects develop (use template)
  - [ ] Keep links and information current
  - [ ] Track which content resonates with audience

**Deliverable:** Live, discoverable portfolio showcasing SE capabilities

---

## Success Metrics

Track these indicators to measure portfolio effectiveness:

- [ ] GitHub repository views/traffic
- [ ] LinkedIn profile views after portfolio launch
- [ ] Feedback from network connections
- [ ] Recruiter/hiring manager engagement
- [ ] Interview requests mentioning specific projects
- [ ] Questions during interviews about portfolio content

---

## Additional Resources

### Tools & References
- VS Code with Claude Code for content development
- GitHub CLI (`gh`) for repository management
- Git for version control
- Markdown preview for README editing
- Draw.io or Excalidraw for architecture diagrams (future)

### Templates Available
- Case study template: `case-studies/template.md`
- Impact statements reference: `impact-statements.md`

### Process for Adding Future Content

1. **New project:**
   - Create `SE-README.md` in the project repo with business context, SE value and use cases
   - Add a pointer in the project's technical README: *"For the Sales Engineering perspective... see [SE-README.md](SE-README.md)."*
   - Copy `case-studies/template.md` to a new file in the portfolio repo
   - Have Claude draft case study and SE-README content based on repo analysis
   - Edit to match voice/tone established in existing content (see editorial patterns above)
   - Add impact statements to `impact-statements.md`
   - Update portfolio README with project summary, SE Perspective link, Technical README link and case study link
   - Update `skills-matrix.md` with new skills/evidence

2. **New impact statements:**
   - Have Claude analyze the repo for capabilities and business context
   - Draft statements following the existing structure (bold key outcome, describe how)
   - Edit to use sales cycle language and frame from SE perspective

---

**Created:** 2026-02-12
**Last Updated:** 2026-02-14
**Status:** ~~Planning~~ → ~~In Progress~~ → ~~Review~~ → Complete (Phase 5 remaining)
