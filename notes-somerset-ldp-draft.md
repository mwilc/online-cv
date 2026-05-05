# CV Refinement Draft — Final Touches

---

## Career Profile — Draft (less waffly, more impact, no numbers)

```yaml
career-profile:
    title: Career Profile
    summary: |
      Cloud infrastructure and AI delivery specialist with a track record of designing and shipping production platforms 
      across healthcare, government, and retail sectors. Started as an RPA Developer on a degree apprenticeship at Capgemini, 
      rapidly progressing through DevOps, platform engineering, and technical architecture roles. Now operating as Senior 
      Platform Engineer at Kainos — pioneering AI-first infrastructure delivery using spec-driven development to build 
      secure, multi-account AWS platforms autonomously.
```

**Why this works:**
- Opens with what you ARE, not generic filler ("dedicated and motivated")
- Sector breadth shows range (healthcare, government, retail)
- Career arc is clear in one sentence
- Ends on the current headline (AI-first delivery)
- No numbers — those are in the experience section
- No soft-skill padding — that's implied by progression

---

## Interests — Format Change

The `interests_new.html` template already exists in `_includes/` and supports title + details (lighter subtitle text), same as education. To use it:

1. Change the sidebar include from `interests.html` → `interests_new.html`
2. Add a `details` field to each interest in the data

**OR** simpler: keep using the sidebar interests but add a main-body `interests` section with the new format. The `interests_new.html` template checks `site.data.data.interests` (top-level, not sidebar).

**Proposed data structure (top-level, not under sidebar):**
```yaml
interests:
    title: Interests
    info:
      - item: AI & Emerging Tech
        details: |
          Exploring agentic AI workflows, LLMs, and how they reshape software delivery.
      - item: Business & Investing
        details: |
          Active investor, interested in markets and have run a number of side projects.
      - item: Sport & Fitness
        details: |
          Former elite-level athlete, still training regularly.
```

**Option:** Keep sidebar interests simple (just titles) OR move interests to main body with the richer format. Your call on placement.

---

## Projects Section — Brainstorm

### The Problem
"Projects" sounds like portfolio pieces / side projects. For someone at your level it should convey **impact and leadership** — things you've driven beyond your day job.

### Naming Options

| Name | Vibe |
|------|------|
| **Contributions & Initiatives** | Professional, shows proactivity |
| **Impact & Leadership** | Bold, CV-friendly |
| **Beyond the Day Job** | Informal, maybe too casual |
| **Initiatives** | Clean, simple |
| **Community & Innovation** | Groups the two themes |
| **Leadership & Innovation** | Strong, senior-sounding |

**My recommendation:** **"Initiatives"** or **"Community & Innovation"** — clean, doesn't sound like hobby projects.

### Content Grouping

Rather than a flat list, think in categories:

**Community & People:**
- DevOps Community Lead — built cross-business DevOps community
- Apprentice Mentorship — guided junior colleagues through structured development
- Schools Outreach — inspired the next generation through talks and assemblies

**Technical Innovation:**
- AI Spec-Driven Development — pioneered and validated agentic AI delivery methodology
- Cloud Compliance Automation — dissertation: automated compliance scanning and remediation in Azure
- Metadata-Driven Platform PoC — built a working PoC for config-driven cloud deployments

### Proposed Draft

```yaml
projects:
    title: Initiatives
    intro: 
    assignments:
      - title: AI Spec-Driven Delivery
        link: "#"
        tagline: "Pioneered and validated a structured AI agent methodology for autonomous infrastructure delivery — proving production-grade outcomes with security and compliance gating."

      - title: DevOps Community
        link: "#"
        tagline: "Founded and led a cross-business DevOps community to share expertise, identify upskilling opportunities, and align with market demands."

      - title: Mentorship & Apprentice Development
        link: "#"
        tagline: "Ongoing mentorship of junior engineers and apprentices — structured sessions, pair programming, and career guidance."

      - title: Cloud Compliance Automation
        link: "#"
        tagline: "University dissertation — designed and built an automated compliance scanning and remediation system in Azure."

      - title: Metadata-Driven Platform PoC
        link: "#"
        tagline: "Built a working proof-of-concept for configuration-driven cloud data platform deployments."
```

**What changed:**
- "AI Spec-Driven Delivery" is now the top item (most impressive, most recent)
- Mentorship expanded to include apprentice angle
- Schools Outreach dropped (less relevant at senior level)
- Work Experience dropped
- Titles are cleaner and more impactful
- Taglines are one punchy sentence each

---

## Summary of Changes to Apply

| Change | Status |
|--------|--------|
| Skills percentages varied | ✅ Applied |
| Career profile rewrite | 📝 Draft above — awaiting approval |
| Interests format (title + subtitle) | 📝 Draft above — needs decision on sidebar vs main body |
| Projects → Initiatives (rename + content) | 📝 Draft above — awaiting approval |
