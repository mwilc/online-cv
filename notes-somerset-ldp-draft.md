# CV Noise Reduction Plan

## Already Done

- [x] Removed phone number
- [x] Removed certifications section entirely
- [x] Updated skills (Python, Terraform, AWS, DevOps & Platform Engineering, Spec-Driven Development, Agentic AI Development, IDPs, Data Platforms, MS Azure)
- [x] Removed college and school from education (kept BSc only)

---

## Remaining: Reduce Noise in Experience Entries

The goal: **2-3 sentences max** describing the project/context, then **clean bullet points** for achievements. No "Key take aways" header needed — just the bullets.

### Senior Platform Architect (Kainos) — TRIM

**Current:** 4 paragraphs + 7 bullets (very long)

**Proposed:**
```yaml
      - role: Senior Platform Architect
        time: 2026 - Present
        company: Kainos
        details: |
            Led a spec-driven AI development spike to design and deliver a multi-account AWS healthcare data platform from the ground up. Pioneered an AI-first delivery approach using structured agent orchestration to autonomously plan, execute, and verify infrastructure — delivering 500+ commits and 130+ requirements through AI-driven development.
            - Pioneered AI-driven infrastructure delivery — agents autonomously planned, coded, tested, and verified with minimal human intervention
            - Architected multi-account AWS platform: Terraform, GitHub Actions CI/CD with OIDC, ephemeral environments, cross-account encryption
            - Delivered E2E data pipeline orchestration (Step Functions + Glue) with PII anonymisation across segregated accounts
            - Implemented security-first patterns: Checkov gating, gitleaks, Fernet encryption, NAT-free VPC endpoints, cross-account KMS
```

### DevOps Lead (Capgemini) — TRIM

**Current:** 4 sentences + 4 bullets

**Proposed:**
```yaml
      - role: DevOps Lead
        time: 2025 - 2026
        company: Capgemini
        details: |
            Led DevOps on a multi-environment AWS data platform using the medallion architecture for a retail sector client. Took ownership of the deployment lifecycle, becoming the gatekeeper for production readiness across 3 environments.
            - Led complex multi-environment deployments and release planning
            - Strengthened DevOps practices and CI/CD processes
            - Took ownership of and improved a fragmented platform
```

### Technical Architect (Capgemini) — TRIM

**Current:** 4 sentences + 4 bullets

**Proposed:**
```yaml
      - role: Technical Architect
        time: 2024 - 2025
        company: Capgemini
        details: |
            Stepped up to solution architect for a data visualisation platform, designing technical solutions and evaluating services, technologies and integrations. Worked closely with senior client stakeholders and wider business teams.
            - Solution design and technical leadership
            - Communication and collaboration with clients
            - Growing delivery and bringing in new business
```

### Platform Lead (Capgemini) — TRIM

**Current:** 3 sentences + 4 bullets

**Proposed:**
```yaml
      - role: Platform Lead
        time: 2023 - 2024
        company: Capgemini
        details: |
            Built and developed an Azure-hosted platform for cutting-edge data visualisation in the health sector. Designed and deployed a metadata-driven system using a CMDB to drive all platform operations.
            - Developed an automated metadata-driven platform
            - Delivered and explained technical work to senior client stakeholders
            - Significant step-up in soft skills: presentation, management, communication
```

### Platform Engineer (Capgemini) — TRIM

**Current:** 4 sentences + 4 bullets

**Proposed:**
```yaml
      - role: Platform Engineer
        time: 2022 - 2023
        company: Capgemini
        details: |
            Maintained and developed the AWS platform hosting a data visualisation solution for a large government department. Identified and solved issues across infrastructure, CI/CD, security, and cost.
            - Managed the entire AWS platform end-to-end
            - Implemented DevOps improvements
            - Acted as team lead during manager's absence
```

### DevOps Engineer (Capgemini) — TRIM

**Current:** 3 sentences + 3 bullets

**Proposed:**
```yaml
      - role: DevOps Engineer
        time: 2021 - 2022
        company: Capgemini
        details: |
            Worked on one of the largest AWS accounts as a DevOps engineer in data migration, delivering bulk data to multiple downstream consumers using Terraform and Jenkins.
            - Deployed AWS Database Migration infrastructure independently
            - Became the main contact for managing migration releases
            - Delivered presentations to wider stakeholders
```

---

## Other Noise to Address

### Career Profile
- Currently good but slightly long. Could trim the last 2 sentences ("A proactive learner..." and "Excellent communicator...") — the CV itself demonstrates these.

### Sidebar Tagline
- Still says "DevOps Lead" — should update to "Senior Platform Architect"

### Projects Section
- Consider trimming to 3-4 most impactful (drop "Work Experience" and "Schools Outreach" — good but less relevant now)
- Keep: DevOps Community Lead, Cloud Compliance Automation, Metadata Driven Platform PoC, Mentorship

### Education
- BSc description is 4 lines — could trim to 2

---

## Summary of Approach

1. Each role: **2-3 sentence context** → **3-4 punchy bullets** (no headers, no fluff)
2. Remove filler words ("Key take aways", "I was given an opportunity", "I was tasked with")
3. Lead with impact, not responsibilities
4. Most recent roles get most detail, older roles get compressed
