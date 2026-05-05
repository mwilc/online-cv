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

## Initiatives Section — Complete Rework

**Name:** Initiatives  
**Tone:** 1-2 sentences per item  
**Approach:** Big buckets, not individual items — each shows a different dimension

### Option A — 5 items, themed

```yaml
projects:
    title: Initiatives
    intro: 
    assignments:
      - title: AI-First Delivery Methodology
        link: "#"
        tagline: "Pioneered spec-driven AI development using structured agent orchestration — validating autonomous infrastructure delivery with full security and compliance gating at production scale."

      - title: SME Digital Transformation
        link: "#"
        tagline: "Providing technology consulting to small and medium businesses — improving digital landscapes across personal training, manufacturing, and service industries."

      - title: Technical Side Projects
        link: "#"
        tagline: "Built a trade copier for automated financial market execution, social media automation tooling, and marketing systems as personal ventures."

      - title: Community & Knowledge Sharing
        link: "#"
        tagline: "Founded and ran a cross-business DevOps community delivering multiple sessions, hosted work experience programmes, and mentored degree apprentices through to qualification."

      - title: Business Development
        link: "#"
        tagline: "Contributed to winning new work through technical pre-sales, solution shaping, and client relationship development."
```

### Option B — 4 items, slightly more concise

```yaml
projects:
    title: Initiatives
    intro: 
    assignments:
      - title: AI-First Delivery Methodology
        link: "#"
        tagline: "Pioneered and validated spec-driven AI agent orchestration for autonomous infrastructure delivery — proving production-grade outcomes with security and compliance gating."

      - title: SME Technology Consulting
        link: "#"
        tagline: "Advising small and medium businesses on their digital landscape — PT studios, manufacturing, and service companies. Building automation, marketing systems, and operational tooling."

      - title: Community, Mentorship & Outreach
        link: "#"
        tagline: "Founded a DevOps community delivering regular sessions, mentored degree apprentices, and ran work experience programmes to develop the next generation of engineers."

      - title: Personal Ventures
        link: "#"
        tagline: "Trade copier for automated market execution, social media automation, and marketing systems — applying engineering skills to personal business projects."
```

### Option C — Maximum impact, 3 big buckets (recommended)

```yaml
projects:
    title: Initiatives
    intro: 
    assignments:
      - title: AI-First Delivery Innovation
        link: "#"
        tagline: "Pioneered spec-driven AI agent methodology for autonomous infrastructure delivery. Validated at production scale with full security gating — now shaping how teams approach AI-augmented engineering."

      - title: Technology Consulting & Ventures
        link: "#"
        tagline: "Advising SMEs on digital transformation (PT, manufacturing, services). Personal builds include trade copiers, social media automation, and marketing systems."

      - title: Community & People Development
        link: "#"
        tagline: "Founded a DevOps community delivering regular knowledge-sharing sessions. Mentored apprentices through to qualification. Ran work experience and outreach programmes."
```

**My take:** Option C is the most impressive — 3 clear buckets that each tell a story. Less noise, more weight. Each one shows a different dimension: technical innovation, entrepreneurial drive, and leadership/people.
