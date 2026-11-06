# AI Solution Architect Certification Prep Course

A free, open, self-paced course that prepares you for the **AI Solution Architect** role and for the vendor exams that test it (AWS, Microsoft, Google Cloud, NVIDIA, Databricks, Anthropic). It combines:

- **8 domains** with learning objectives, core concepts, decision frameworks and curated reading from GitHub and official docs.
- **Hands-on labs** you can run on a laptop with free tiers.
- **Free credentials** mapped to each domain from the [Free AI Certifications Tracker](../free-certifications/README.md).
- **Review questions** per domain, a **60-question mock exam** and a **capstone** design review.

> [!IMPORTANT]
> This is a study course, not an exam dump. All questions are original. Never use real exam content, and never let a bot or agent take a course or exam for you.

## Contents

- [Who this is for](#who-this-is-for)
- [Exam blueprint](#exam-blueprint)
- [Study plans](#study-plans)
- [Domains](#domains)
- [How to use this course](#how-to-use-this-course)
- [Earn the completion badge](#earn-the-completion-badge)

## Who this is for

| You are | Start at |
| --- | --- |
| Software or cloud architect new to AI | Domain 1, then follow the 10-week plan. |
| ML or data engineer moving into architecture | Skim Domain 1, start properly at Domain 2. |
| Pre-sales or solutions engineer | Domains 2, 3 and 8 first, then the rest. |
| Already shipping LLM apps | Take the [mock exam](mock-exam.md) first and study your weakest domains. |

Prerequisites: comfort with one programming language (Python preferred), HTTP APIs, basic cloud concepts (VPC, IAM, managed services) and reading architecture diagrams.

## Exam blueprint

The mock exam and the review questions follow this weighting. It mirrors what vendor AI architect and AI engineer exams emphasize in late 2026: designing grounded, agentic, secure and cost-aware systems.

| # | Domain | Weight | Core question an architect must answer |
| :-: | --- | :-: | --- |
| 1 | [AI and LLM Foundations for Architects](01-ai-foundations.md) | 10% | What can these models do, and what will they get wrong? |
| 2 | [Discovery, Use-Case Framing and Business Value](02-discovery-and-value.md) | 10% | Should we build this, and how will we know it worked? |
| 3 | [Generative AI Reference Architectures](03-reference-architectures.md) | 20% | Which pattern fits: prompt, RAG, workflow, agent or fine-tune? |
| 4 | [Data Architecture for AI](04-data-architecture.md) | 12% | How does enterprise data reach the model safely and fresh? |
| 5 | [Model Platform, Serving and Cost](05-model-platform-and-cost.md) | 12% | Which model, where does it run, and what does it cost at scale? |
| 6 | [Evaluation, Observability and LLMOps](06-evaluation-and-llmops.md) | 12% | How do we prove quality before and after launch? |
| 7 | [Security, Safety and Responsible AI](07-security-and-governance.md) | 14% | What can go wrong, who is accountable, and what are the controls? |
| 8 | [Cloud Implementation and Well-Architected Review](08-cloud-implementation.md) | 10% | How does the design map to AWS, Azure or Google Cloud services? |

Passing standard for the mock exam: **70%** overall and at least **60%** in every domain.

## Study plans

| Plan | Hours per week | Schedule |
| --- | :-: | --- |
| Sprint | 15-20 | 4 weeks: two domains per week, mock exam and capstone in week 4. |
| Standard | 8-10 | 10 weeks: see [study-plan.md](study-plan.md). |
| Part-time | 4-5 | 16 weeks: one domain every two weeks. |

## Domains

Each domain file has the same structure:

1. **Learning objectives** you can check off.
2. **Core concepts** with tables and decision frameworks.
3. **Architecture patterns and anti-patterns.**
4. **Reading list** from GitHub and official documentation.
5. **Free credentials** to earn for this domain.
6. **Hands-on lab.**
7. **Review questions** with hidden answers.

After the domains:

- [Mock exam](mock-exam.md): 60 scenario questions, 120 minutes.
- [Capstone](capstone.md): a full solution design with ADRs and a design review rubric.
- [Vendor certifications](../certifications.md): which paid exam to take next and how this course maps to it.

## How to use this course

1. Fork the repository so you can tick checkboxes and keep notes.
2. Take the [mock exam](mock-exam.md) cold to find your baseline. Do not look at the answers yet.
3. Work through the domains in order. Do every lab: architects who have built the thing give better answers.
4. Earn the free credentials listed in each domain as you go.
5. Retake the mock exam. Aim for 80% before booking a vendor exam.
6. Complete the [capstone](capstone.md) and ask a peer to review it with the rubric.

## Earn the completion badge

When you pass the mock exam and complete the capstone, add this badge to your profile README and link it to your capstone repository:

```markdown
[![AI Solution Architect Prep](https://img.shields.io/badge/AI%20Solution%20Architect-Prep%20Complete-0b7285)](https://github.com/EldanGS/awesome-ai-architect/tree/main/course)
```

The badge is a self-declared record of study, not a vendor certification. Pair it with a vendor exam from [certifications.md](../certifications.md) for a recognized credential.
