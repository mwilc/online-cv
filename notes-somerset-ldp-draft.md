# CV Update Draft — Senior Platform Architect (Kainos)

## New Experience Entry

**Role:** Senior Platform Architect  
**Time:** 2026 - Present  
**Company:** Kainos  
**Project:** Healthcare data platform — NHS client  
**Cloud:** AWS (multi-account, multi-environment)

---

## Draft Entry

```yaml
      - role: Senior Platform Architect
        time: 2026 - Present
        company: Kainos
        details: |
            Led a spec-driven AI development spike to design, build and deliver a multi-account AWS healthcare data platform for an NHS client from the ground up.
            Pioneered an innovative AI-first delivery approach using the GSD (Get Shit Done) framework — a structured methodology that leverages AI agents to autonomously plan, execute, verify, and ship infrastructure at unprecedented velocity.
            Through this approach, delivered a number of major milestones resulting in 500+ commits and 130+ requirements satisfied — all orchestrated through AI-driven spec-driven development.
            The platform ingests sensitive patient data from healthcare providers, processes it through a medallion architecture (landing → bronze), and anonymises PII using Fernet encryption and a Master Patient Index across segregated AWS accounts.
            Key take aways
            - Pioneered AI-driven infrastructure delivery using spec-driven development (GSD framework) — AI agents autonomously planned phases, executed code, ran quality gates, and verified outcomes with minimal human intervention
            - Demonstrated that AI-augmented delivery can produce production-grade, security-compliant infrastructure at 5-10x the velocity of traditional approaches
            - Architected a multi-account AWS platform from scratch: Terraform IaC, GitHub Actions CI/CD with OIDC, 4 LZA accounts, ephemeral environment isolation
            - Built reusable Terraform modules for composite pipelines (Step Functions + Glue), KMS encryption, landing zone ingress, and S3 event triggers
            - Delivered end-to-end data pipeline orchestration (ingest → enrich → load) across dual AWS accounts with cross-account encryption and EventBridge automation
            - Implemented security-first patterns: Checkov gating (HIGH+ severity), gitleaks scanning, Fernet PII anonymisation, NAT-free VPC endpoints, cross-account KMS
            - Established engineering standards: conventional commits, Docker-based tooling, automated documentation generation, SemVer releases, and quality-gated CI/CD
```

---

## Career Profile update suggestion

```yaml
career-profile:
    title: Career Profile
    summary: |
      Dedicated and motivated professional with a strong background in cloud infrastructure, DevOps, and AI-driven delivery.
      Finished A levels and secured a degree apprenticeship at Capgemini, where I started as an RPA Developer 
      and quickly transitioned to Cloud and DevOps. Completed a degree apprenticeship and have since worked across 
      multiple public sector clients and supported delivery on a number of internal initiatives. Now operating as 
      Senior Platform Architect at Kainos, leading innovative AI-first delivery approaches — most recently using 
      spec-driven AI development to design and deliver a multi-account AWS healthcare data platform from scratch, 
      shipping multiple major milestones and satisfying 130+ requirements. Proficient at developing and applying knowledge in cutting-edge 
      technologies to deliver innovative solutions and drive operational excellence. A proactive learner committed 
      to continuous improvement and professional development. Excellent communicator and team player with strong 
      problem-solving skills and a passion for mentoring and developing junior talent.
```

---

## Key technologies & capabilities to highlight

- **AI Delivery:** GSD framework, spec-driven development, AI agent orchestration, autonomous planning/execution/verification
- **IaC:** Terraform (reusable modules, state management, multi-account)
- **CI/CD:** GitHub Actions, OIDC, SemVer, conventional commits, quality-gated pipelines
- **AWS Services:** S3, KMS, Glue, Step Functions, DynamoDB, VPC Endpoints, EventBridge, Secrets Manager, CloudWatch, IAM, SSO
- **Security:** Checkov, gitleaks, Fernet encryption, cross-account KMS, TLS enforcement
- **Tooling:** Docker, TFLint, terraform-docs, Makefile-driven workflows
- **Patterns:** Medallion architecture, ephemeral environments, landing zone ingress, composite pipeline modules

---

## Notes

- The headline story is **AI-driven delivery innovation** — you ran this as a spike proving AI agents can deliver production-grade infrastructure autonomously
- "500+ commits, 130+ requirements, multiple milestones" demonstrates the velocity AI delivery enables
- The GSD framework provided structure: phases → plans → execution → verification — ensuring AI output met quality and security standards
- The technical platform (AWS, Terraform, healthcare data, PII encryption) provides the credibility backdrop
- Healthcare/NHS is a strong sector for public sector credibility (keep client name generic)
- The spike ran alongside traditional AI-assisted development (chat/prompts), making it a direct comparison of methodologies
