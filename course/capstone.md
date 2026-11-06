# Capstone: Design Review for an Enterprise AI Platform

**Time: 15-25 hours** · [Back to course](README.md)

Produce the design package an architecture review board would expect, defend it with a peer, and publish it in your own repository as portfolio evidence.

## Scenario

*Northwind Mutual* is a fictional insurer with 6,000 employees in the EU and US. Leadership wants, within two quarters:

1. **Claims assistant** for 800 claims handlers: answers policy and procedure questions from 40,000 documents (PDF, Word, wiki) with citations; documents have department and country permissions.
2. **First notice of loss (FNOL) agent** for customers on the website: collects claim details, checks policy status through an internal API, creates a claim draft, and books an adjuster call. No payout decisions.
3. **Platform:** both apps, and future ones, must share model access, guardrails, logging and cost controls.

Constraints:

- EU customer data must be processed in the EU.
- Policy administration runs on-premises behind an API gateway; the CRM is SaaS.
- Security requires SSO, least privilege, audit logs retained for 7 years, and no customer data used for model training.
- Budget target: under 40,000 USD per month run cost at full adoption (excluding staff).
- The claims director wants measurable impact: average handling time down 20%.

## Deliverables

| # | Deliverable | Format |
| :-: | --- | --- |
| 1 | Problem statement, success criteria and baseline assumptions | 1 page |
| 2 | C4 context and container diagrams for both apps and the shared platform | Diagrams as code (Mermaid, Structurizr or Diagrams) |
| 3 | Data architecture: ingestion, chunking, index design, permission model, freshness and deletion | 1-2 pages plus a diagram |
| 4 | Agent design for FNOL: tools, MCP servers or APIs, state, budgets, human handoff | Sequence diagram plus tool table |
| 5 | Model and platform choice with cost model at full adoption | Spreadsheet plus ADR |
| 6 | Evaluation plan: datasets, metrics, thresholds, CI gate, online monitoring | 1-2 pages |
| 7 | Threat model mapped to OWASP LLM Top 10 and responsible AI assessment (including EU AI Act classification) | Table |
| 8 | Well-architected review against the six pillars with open risks | Table |
| 9 | At least five ADRs | Markdown files |
| 10 | Rollout plan: pilot, success gates, change management, production readiness | 1 page |
| 11 | Optional: working prototype of the claims assistant RAG path | Code repository |

## Suggested repository layout

```text
northwind-ai-architecture/
├── README.md               # Executive summary and links
├── 01-problem.md
├── diagrams/
├── 03-data-architecture.md
├── 04-fnol-agent.md
├── 05-cost-model.xlsx
├── 06-evaluation-plan.md
├── 07-threat-model.md
├── 08-well-architected.md
├── adr/
│   ├── 0001-model-platform.md
│   ├── 0002-vector-store.md
│   ├── 0003-ai-gateway.md
│   ├── 0004-agent-framework.md
│   └── 0005-eu-data-residency.md
├── 10-rollout.md
└── prototype/              # optional
```

## Review rubric

A peer reviewer scores each criterion from 0 to 4. Pass at **36 of 48** with no criterion below 2.

| Criterion | 4: Excellent | 2: Acceptable | 0: Missing |
| --- | --- | --- | --- |
| Problem and success criteria | Baselined, measurable, owned. | Measurable but no baseline. | Vague goals. |
| Pattern choice | Simplest adequate pattern, alternatives compared. | Reasonable pattern, little justification. | Over- or under-engineered without reason. |
| Data and permissions | ACL propagation, freshness, deletion and lineage covered. | Permissions covered, freshness thin. | No permission model. |
| Agent safety | Budgets, scoped tools, approvals, handoff, audit. | Some controls. | Unbounded agent. |
| Model and cost | Cost model with levers and routing; within budget. | Cost estimated roughly. | No cost model. |
| Evaluation | Datasets, metrics, thresholds, CI gate, online monitoring. | Offline eval only. | No evaluation plan. |
| Security and threat model | All relevant OWASP risks mapped to controls. | Main risks covered. | Generic statements. |
| Responsible AI and compliance | Risk tier, oversight, transparency, residency addressed. | Partially addressed. | Missing. |
| Cloud mapping and networking | Concrete services, private networking, regions verified. | Services named, gaps in networking. | No mapping. |
| Platform and reuse | Landing zone serves future apps. | Shared gateway only. | Each app isolated. |
| Decisions | Five or more clear ADRs with consequences. | Fewer or thin ADRs. | None. |
| Communication | Clear diagrams and executive summary a non-expert can follow. | Understandable with effort. | Hard to follow. |

## Defend it

Present your design in 20 minutes to a peer acting as the review board, then take 20 minutes of questions. Expect questions like:

- What happens when the policy API is down during an FNOL conversation?
- How do you prove a claims handler in Germany cannot see US-only procedures?
- What is the cost at twice the expected traffic, and what would you cut first?
- Which single change would most reduce risk if the security team rejected your design?

Record the questions you could not answer well and update the design. That list is your best study guide for the vendor exam.
