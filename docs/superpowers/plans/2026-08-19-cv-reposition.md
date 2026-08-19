# CV Repositioning Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Reposition Matt Wilcox's online CV from a Platform/DevOps engineering profile to a customer-facing Cloud Solutions Consultant / Pre-Sales / Technical Business Development profile while retaining technical credibility.

**Architecture:** Content-driven change in the existing Jekyll template. One new include for the Commercial Impact section; the main CV data file and page order are updated. No build logic or styling changes.

**Tech Stack:** Jekyll, YAML front matter, Liquid includes, Bootstrap-based Sass theme.

## Global Constraints
- Preserve truthfulness: no invented revenue figures, quotas, or responsibilities.
- Keep role titles factually accurate; only the sidebar tagline may change.
- Maintain strong AWS/AI technical credibility without reading like a technical architecture document.
- Follow existing Jekyll include pattern: `_includes/<section>.html` + `site.data.data.<section>`.
- Use Conventional Commits.
- Create feature branch `feat/cv-reposition` before editing.

---

### Task 1: Create feature branch

**Files:**
- Modify: none (git operation)

**Interfaces:**
- Consumes: current branch `main`
- Produces: local branch `feat/cv-reposition`

- [ ] **Step 1: Ensure main is up to date**

Run:
```bash
git checkout main && git pull origin main
```
Expected: working tree clean, `main` up to date.

- [ ] **Step 2: Create feature branch**

Run:
```bash
git checkout -b feat/cv-reposition
```
Expected: branch `feat/cv-reposition` checked out.

---

### Task 2: Add Commercial Impact include template

**Files:**
- Create: `_includes/commercial-impact.html`

**Interfaces:**
- Consumes: `site.data.data.commercial-impact`
- Produces: rendered HTML for Commercial Impact section

- [ ] **Step 1: Create the include file**

Create `_includes/commercial-impact.html` with:
```liquid
{% assign commercial-impact = site.data.data.commercial-impact %}
{% if commercial-impact %}
<section class="section commercial-impact-section">

  <h2 class="section-title">
    <span class="fa-stack fa-xs">
      <i class="fas fa-circle fa-stack-2x"></i>
      <i class="fas fa-chart-line fa-stack-1x fa-inverse"></i>
    </span>
    {{ commercial-impact.title }}
  </h2>

  {% if commercial-impact.intro %}
  <div class="intro">
    {{ commercial-impact.intro | markdownify }}
  </div><!--//intro-->
  {% endif %}

  <div class="impact-list">
    {% for item in commercial-impact.items %}
    <div class="item">
      <span class="impact-title">{{ item.title }}</span>
      {% if item.detail %}
      — <span class="impact-detail">{{ item.detail }}</span>
      {% endif %}
    </div><!--//item-->
    {% endfor %}
  </div><!--//impact-list-->

</section><!--//section-->
{% endif %}
```

- [ ] **Step 2: Verify file exists**

Run:
```bash
ls -la _includes/commercial-impact.html
```
Expected: file listed.

---

### Task 3: Insert Commercial Impact section into page order

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: existing includes (`career-profile.html`, etc.)
- Produces: page renders Career Profile → Commercial Impact → Education → Experiences → Certifications → Projects → OSS → Publications → Skills

- [ ] **Step 1: Add include after Career Profile**

Replace in `index.html`:
```liquid
---
layout: default
---


{% include career-profile.html %}
```
with:
```liquid
---
layout: default
---


{% include career-profile.html %}

{% include commercial-impact.html %}
```

- [ ] **Step 2: Verify Jekyll still parses**

Run:
```bash
bundle exec jekyll build --strict_front_matter 2>&1 | head -30
```
Expected: build completes with no Liquid/YAML errors.

---

### Task 4: Rewrite `_data/data.yml` content

**Files:**
- Modify: `_data/data.yml`

**Interfaces:**
- Consumes: existing schema for `sidebar`, `career-profile`, `experiences`, `projects`, `skills`
- Produces: updated YAML that drives repositioned CV copy

- [ ] **Step 1: Update sidebar tagline**

Replace:
```yaml
    tagline: Senior Platform Engineer
```
with:
```yaml
    tagline: Cloud Solutions Consultant
```

- [ ] **Step 2: Rewrite career profile summary**

Replace the `career-profile.summary` block with:
```yaml
career-profile:
    title: Career Profile
    summary: |
      Cloud Solutions Consultant with an engineering backbone and a growing track record in customer engagement, account growth, and commercial delivery. I help organisations turn complex technology into actionable business outcomes — whether that means shaping cloud strategy, running executive workshops, securing partner funding, or building propositions that open new revenue streams.

      My background is hands-on: AWS platform delivery, AI-first engineering, data platforms, and DevOps at scale. Over time I have moved closer to the commercial edge of the business — managing AWS partner relationships, identifying growth opportunities in existing accounts, negotiating resources, and pitching solutions directly to senior stakeholders. I am now pursuing consulting, pre-sales, and business development roles where technical credibility and commercial impact meet.
```

- [ ] **Step 3: Add commercial impact section data**

Insert after `career-profile` and before `education`:
```yaml
commercial-impact:
    title: Commercial Impact
    intro: |
      Selected achievements that show how I create value beyond delivery — through funding, revenue, account growth, and stakeholder influence.
    items:
      - title: Secured AWS funding and MAP credits
        detail: As Deputy AWS Partner Lead, managed the AWS relationship and unlocked funding and migration acceleration incentives to support client engagements.

      - title: Generated additional billable revenue
        detail: Built a business case that closed a contractor-reliance gap and helped grow the delivery team from 2 to 6 engineers, securing an extra £2,500/day in billables.

      - title: Converted an unfunded resource into a permanent billable role
        detail: Negotiated two unfunded engineers onto an understaffed project via internal resourcing; converted one into a permanent billable position adding £750/day.

      - title: Built and pitched a new AI proposition
        detail: Developed a Bedrock RAG proposition enabling project managers to query project data for risk and trend analysis, and pitched it to stakeholders.

      - title: Supported account growth across existing and new clients
        detail: Identified and pursued growth opportunities within existing accounts while growing Capgemini's AWS practice alongside the partner team.

      - title: Expanded delivery capability
        detail: Grew teams, secured investment, and shaped resourcing decisions through internal negotiation and stakeholder management.

      - title: Managed strategic relationships
        detail: Owned client and AWS relationships, facilitated workshops, and acted as the bridge between technical delivery and commercial outcomes.

      - title: Facilitated client workshops
        detail: Ran discovery and solution workshops with senior client stakeholders to surface opportunities and align delivery with business priorities.
```

- [ ] **Step 4: Reposition experiences**

Replace the entire `experiences` block with:
```yaml
experiences:
    title: Experiences
    info:
      - role: Senior Platform Engineer
        time: 2026 - Present
        company: Kainos
        details: |
            Shaped and delivered a multi-account AWS healthcare data platform from first principles, while pioneering an AI-first consulting delivery model that dramatically accelerated proposition development and client outcomes.
            - Identified the opportunity to apply agentic AI to infrastructure delivery, then built and pitched the approach internally — delivering 130+ requirements and 500+ commits with minimal human intervention
            - Facilitated scoping conversations and shaped the platform proposition for healthcare data workloads
            - Influenced architecture and security decisions across segregated AWS accounts, balancing technical rigour with delivery speed
            - Drove delivery efficiency that strengthened the team's ability to respond to new commercial opportunities

      - role: Deputy AWS Partner Lead
        time: 2025 - 2026 (concurrent)
        company: Capgemini
        details: |
            Owned Capgemini's AWS relationship and grew the AWS practice by connecting partner strategy to account opportunities, workshops, and funded programmes.
            - Managed client and AWS relationships, identifying opportunities and positioning Capgemini solutions with stakeholders
            - Secured AWS funding and MAP credits to support client migration and modernisation initiatives
            - Built and pitched a Bedrock RAG proposition enabling project managers to query project data for risk and trend analysis
            - Grew AWS practice visibility across existing and new accounts through propositions, workshops, and partner engagement

      - role: DevOps Lead
        time: 2025 - 2026
        company: Capgemini
        details: |
            Led DevOps for a retail-sector AWS data platform, becoming the trusted gatekeeper for production readiness and the primary link between technical teams and client stakeholders.
            - Owned release planning and production-readiness decisions across three environments
            - Strengthened client confidence by improving platform stability and delivery discipline
            - Identified and removed blockers that were slowing account delivery, enabling the team to take on more scope

      - role: Technical Architect
        time: 2024 - 2025
        company: Capgemini
        details: |
            Stepped up as solution architect for a data visualisation platform, focusing on growing delivery capacity and aligning technical solutions with client and commercial priorities.
            - Negotiated two unfunded engineers onto an understaffed project through internal stakeholder influence
            - Converted one into a permanent billable role, adding £750/day in billables
            - Influenced senior client stakeholders and wider business teams on solution direction
            - Balanced solution design decisions with delivery capacity and account health

      - role: Platform Lead
        time: 2023 - 2024
        company: Capgemini
        details: |
            Led an Azure-hosted data visualisation platform in the health sector, with increasing exposure to senior stakeholders and the commercial side of account delivery.
            - Shaped and delivered a metadata-driven platform that simplified operations and reduced ongoing service risk
            - Presented technical direction and trade-offs to senior client stakeholders, building trust and account credibility
            - Developed propositions and communication skills that laid the groundwork for later consulting and partner-facing work

      - role: Platform Engineer
        time: 2022 - 2023
        company: Capgemini
        details: |
            Managed the AWS platform for a large government data visualisation solution, while identifying and securing investment to grow the delivery team and account capability.
            - Built a business case that identified and closed a contractor-reliance gap
            - Helped grow the delivery team from 2 to 6 engineers, securing an extra £2,500/day in billables
            - Owned the end-to-end AWS platform and acted as team lead during the manager's absence
            - Maintained and presented the platform's health to stakeholders, influencing continued investment

      - role: DevOps Engineer
        time: 2021 - 2022
        company: Capgemini
        details: |
            Delivered bulk data migration services on one of Capgemini's largest AWS accounts, becoming the main point of contact for migration releases and stakeholder updates.
            - Deployed and managed AWS Database Migration infrastructure as the trusted release owner
            - Became the primary contact for planning and communicating migration releases to downstream consumers
            - Delivered presentations to wider stakeholders, building early experience in customer-facing communication
```

- [ ] **Step 5: Tighten project taglines**

Replace `projects.assignments` taglines with:
```yaml
projects:
    title: Initiatives
    intro: 
    assignments:
      - title: AI-First Delivery Innovation
        link: "#"
        tagline: "Pioneered a spec-driven, agentic approach to cloud delivery — positioning teams to respond faster to client opportunities and reduce proposition-to-production time."

      - title: Technology Consulting & Advisory
        link: "#"
        tagline: "Advise business SMEs on digital transformation. Personal ventures span trade automation, social media systems, and marketing platforms, strengthening commercial and product instincts."

      - title: Community & People Development
        link: "#"
        tagline: "Founded a DevOps community and ran regular knowledge-sharing sessions. Mentored apprentices to qualification and led outreach programmes that grew internal capability."
```

- [ ] **Step 6: Rework skills**

Replace `skills.toolset` with:
```yaml
skills:
    title: Skills &amp; Proficiency

    toolset:
      - name: Business Development
        level: 85%

      - name: Account Growth
        level: 88%

      - name: Stakeholder Management
        level: 86%

      - name: Workshop Facilitation
        level: 84%

      - name: Solution Selling
        level: 80%

      - name: Customer Discovery
        level: 82%

      - name: Executive Communication
        level: 83%

      - name: Proposal Development
        level: 80%

      - name: Technical Consulting
        level: 85%

      - name: Cloud Strategy
        level: 82%

      - name: Amazon Web Services
        level: 85%

      - name: Agentic AI Development
        level: 80%

      - name: Platform Engineering
        level: 80%

      - name: DevOps
        level: 78%

      - name: Terraform
        level: 82%

      - name: Data Platforms
        level: 72%

      - name: Microsoft Azure
        level: 66%

      - name: Python
        level: 76%
```

- [ ] **Step 7: Validate YAML syntax**

Run:
```bash
ruby -e "require 'yaml'; YAML.load_file('_data/data.yml'); puts 'YAML OK'"
```
Expected: `YAML OK`

- [ ] **Step 8: Build Jekyll site**

Run:
```bash
bundle exec jekyll build 2>&1 | tail -20
```
Expected: build succeeds, no YAML/Liquid errors.

---

### Task 5: Review rendered output

**Files:**
- Verify: `_site/index.html` (generated)

**Interfaces:**
- Consumes: built site
- Produces: visual confirmation or list of issues

- [ ] **Step 1: Serve site locally**

Run:
```bash
bundle exec jekyll serve --detach --host 127.0.0.1 --port 4000
```

- [ ] **Step 2: Check key sections render**

Open `http://127.0.0.1:4000` and confirm:
1. Sidebar tagline reads "Cloud Solutions Consultant".
2. Career Profile opens with consulting/commercial narrative and career-direction statement.
3. Commercial Impact section appears immediately after Career Profile.
4. Experience entries lead with business outcomes, not implementation detail.
5. Skills prioritise business/consulting skills, with technical skills secondary.
6. No broken YAML/Liquid output visible on the page.

- [ ] **Step 3: Stop local server**

Run:
```bash
pkill -f "jekyll serve" || true
```

---

### Task 6: Commit changes

**Files:**
- Modify: `_data/data.yml`, `index.html`
- Create: `_includes/commercial-impact.html`

**Interfaces:**
- Consumes: updated files
- Produces: committed feature branch

- [ ] **Step 1: Stage changes**

Run:
```bash
git add _data/data.yml index.html _includes/commercial-impact.html docs/superpowers/specs/2026-08-19-cv-reposition-design.md docs/superpowers/plans/2026-08-19-cv-reposition.md
```

- [ ] **Step 2: Commit with Conventional Commits**

Run:
```bash
git commit -m "feat(cv): reposition profile toward cloud solutions and pre-sales consulting

- Update tagline to Cloud Solutions Consultant
- Rewrite career profile for customer-facing commercial impact
- Add Commercial Impact section with funding, revenue, and account growth
- Reposition experience descriptions to lead with business outcomes
- Rework skills to prioritise consulting and business development
- Tighten project taglines around advisory and delivery innovation"
```

---

## Self-Review

**1. Spec coverage:**
- ✅ Career Profile rewrite — Task 4 Step 2
- ✅ Reposition Experience — Task 4 Step 4
- ✅ Emphasise commercial achievements — Task 4 Steps 2-4
- ✅ New Commercial Impact section — Tasks 2, 3, 4 Step 3
- ✅ Skills section rework — Task 4 Step 6
- ✅ Reduce technical noise — Task 4 Step 4
- ✅ Career direction statement — Task 4 Step 2
- ✅ Preserve truthfulness — Global Constraints + Task 4 Step 4

**2. Placeholder scan:**
- No TBD/TODO/"fill in details".
- No vague "add appropriate" instructions.
- All code blocks contain literal content.

**3. Type consistency:**
- YAML keys (`commercial-impact`, `career-profile`, `experiences`, `projects`, `skills`) match existing Jekyll/Liquid usage.
- Include file name matches include call.
