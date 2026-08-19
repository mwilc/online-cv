# CV Repositioning Design

## Goal
Rewrite Matt Wilcox's online CV so it positions him for customer-facing, commercially focused technology roles (Cloud Solutions Consultant, Pre-Sales Consultant, Technical Business Development Consultant, Partner Solutions Architect, Customer-facing Technology Consultant) while preserving technical credibility and truthfulness.

## Scope
- Modify content in `_data/data.yml` only, with one new include (`_includes/commercial-impact.html`) and one page-order change in `index.html`.
- No visual redesign, no new assets, no role-title changes beyond the sidebar tagline.
- Role names remain factually accurate; descriptions are reframed to lead with commercial outcomes.

## Proposed Changes

### 1. Sidebar tagline
Change `Senior Platform Engineer` to `Cloud Solutions Consultant`.

### 2. Career Profile rewrite
Rewrite the profile to:
- State the intentional move toward customer-facing and commercially focused roles.
- Emphasise commercial impact, customer engagement, account growth, stakeholder management, business development, and technical consulting.
- Retain strong AWS/AI technical credibility as an underpinning, not the headline.

### 3. New Commercial Impact section
- Create `_includes/commercial-impact.html`.
- Add `commercial-impact` block to `_data/data.yml` with achievements supported by existing CV evidence:
  - Secured AWS funding and MAP credits.
  - Generated additional billable revenue (convert contractor-reliance gap → extra £2,500/day billables; negotiate unfunded engineer → permanent billable role adding £750/day).
  - Supported account growth through AWS partner lead responsibilities.
  - Built and pitched a Bedrock RAG proposition.
  - Expanded delivery capability from 2 to 6 engineers.
  - Managed strategic AWS and client relationships.
  - Facilitated client workshops.
- Insert into `index.html` immediately after the Career Profile.

### 4. Experience repositioning
For every role in `_data/data.yml.experiences`:
- Move commercial impact ahead of technical implementation.
- Lead with business outcomes: revenue, growth, stakeholder influence, workshops, funding, partnerships, propositions.
- Reduce deep technical implementation detail (OIDC, KMS, encryption specifics, low-level Terraform).
- Convert engineering verbs into consulting/commercial verbs where factually justified.
- Retain enough AWS/platform/AI detail to maintain credibility.

### 5. Skills rework
- Reorder and re-balance `skills.toolset` in `_data/data.yml`.
- Prioritise: Business Development, Account Growth, Stakeholder Management, Workshop Facilitation, Customer Discovery, Solution Selling, Executive Communication, Proposal Development, Technical Consulting, Cloud Strategy.
- Move purely technical skills into a secondary grouping.

### 6. Projects refresh
- Tighten project taglines in `_data/data.yml.projects` to reinforce consulting and commercial impact.
- Keep the same three initiatives.

### 7. Career direction statement
- Integrate into the Career Profile and/or Commercial Impact intro.
- Explain the engineering background, the increasing customer engagement focus, and the target consulting/pre-sales/business-development direction.

## Design Approval
- Approved approach: Option B (add standalone Commercial Impact section, keep role titles factual, rewrite content).
- Commercial Impact placement: immediately after Career Profile.
- Sidebar tagline: `Cloud Solutions Consultant`.
