# Domain 2: Discovery, Use-Case Framing and Business Value

**Weight: 10%** · **Time: 6-8 hours** · [Back to course](README.md)

Most failed AI projects fail before the first line of code: the wrong problem, no baseline, no owner, or no way to measure success. This domain is about deciding **whether** and **what** to build.

## Learning objectives

- [ ] Run a structured discovery session and capture problem, users, data, constraints and success metrics.
- [ ] Score and prioritize use cases on value, feasibility and risk.
- [ ] Decide build, buy or extend (off-the-shelf copilot, platform agent builder, or custom).
- [ ] Build a simple ROI and total cost of ownership model for an AI solution.
- [ ] Define measurable success criteria and a baseline before a pilot starts.
- [ ] Plan a pilot-to-production path with change management.

## Core concepts

### Discovery checklist

| Area | Questions to ask |
| --- | --- |
| Problem | What decision or task is slow, costly or error-prone today? How often does it happen? |
| Users | Who uses the output? What do they do with it? What happens when it is wrong? |
| Baseline | How long does it take today, at what cost, with what error rate? |
| Data | Where does the needed knowledge live? Who owns it? How fresh, clean and permissioned is it? |
| Integration | Which systems must be read or written? Are there APIs? |
| Constraints | Regulation, data residency, latency, languages, budget, deadlines. |
| Risk | What is the worst plausible failure? Is a human in the loop? |
| Ownership | Who is the business owner and who will run it after launch? |

### Use-case scoring

Score each candidate from 1 to 5 and multiply by the weight.

| Criterion | Weight | 1 means | 5 means |
| --- | :-: | --- | --- |
| Business value | 30% | Nice to have. | Measurable revenue, cost or risk impact. |
| Data readiness | 20% | Data unknown or locked. | Clean, accessible, permissioned. |
| Technical feasibility | 20% | Unproven, research-grade. | Known pattern (RAG, extraction, routing). |
| Risk tolerance | 15% | Errors cause harm or legal exposure. | Errors are cheap and caught by a human. |
| Time to value | 15% | More than 6 months. | Pilot in under 6 weeks. |

Start with high-value, low-risk use cases where a human reviews outputs (drafting, summarizing, search, triage). Save fully autonomous actions for later.

### Build, buy or extend

| Option | Choose when | Watch out for |
| --- | --- | --- |
| Buy an off-the-shelf assistant (enterprise chat, coding assistant, CRM or ITSM copilot) | Generic productivity use case, fast rollout. | Limited customization, data boundaries, per-seat cost. |
| Extend a platform (agent builders in Salesforce, ServiceNow, Microsoft Copilot Studio, Google Agentspace and similar) | Workflow lives inside that platform. | Platform lock-in, licensing, governance across platforms. |
| Build custom on model APIs | Differentiating workflow, proprietary data, complex integration. | You own evaluation, security, operations and cost. |
| Self-host open models | Hard residency or air-gap needs, or very high volume. | Serving, scaling, safety tuning and talent cost. |

### ROI and total cost of ownership

```text
Annual value  = volume per year x time saved per task x loaded hourly cost
              + error reduction value + revenue uplift
Annual cost   = model usage (tokens x price) + infrastructure (vector DB, compute, gateway)
              + build cost amortized + run cost (people, evaluation, monitoring) + licenses
ROI           = (annual value - annual cost) / annual cost
```

Worked example: 50,000 support tickets per year, 6 minutes saved each, 40 USD loaded hourly cost gives 200,000 USD per year in time saved. If model usage is 0.02 USD per ticket (1,000 USD), infrastructure 15,000 USD and run cost 60,000 USD, annual cost is 76,000 USD and ROI is about 1.6x. The model bill is rarely the largest line; people and operations usually are.

### Success criteria

Good criteria are **specific, measured against a baseline, and agreed before the pilot**:

- Quality: "Answers are rated correct and grounded in at least 90% of a 200-question evaluation set."
- Efficiency: "Median handle time falls from 9 to 6 minutes for pilot agents."
- Adoption: "60% of pilot users use the assistant weekly by week 4."
- Safety: "Zero responses expose data the user is not entitled to see in red-team testing."

## Patterns and anti-patterns

**Patterns**

- Pilot with a small, motivated user group and a control group for comparison.
- Write a one-page problem statement and get the business owner to sign it.
- Plan change management from day one: training, feedback channel, champions.

**Anti-patterns**

- "We need an AI strategy" with no named process or owner.
- Measuring only model accuracy and never business outcomes.
- Choosing a fully autonomous agent for a process with high error cost as the first project.

## Reading list

- [Generative AI for Beginners, lesson 1-2](https://github.com/microsoft/generative-ai-for-beginners) - Startup scenario and use-case framing for generative AI.
- [Machine Learning Systems Design](https://github.com/chiphuyen/machine-learning-systems-design) - Chip Huyen's booklet on framing ML problems and project setup.
- [Rules of Machine Learning](https://developers.google.com/machine-learning/guides/rules-of-ml) - Google's practical guidance, starting with "do you need ML at all".
- [Architecture Decision Records](https://github.com/architecture-decision-record/architecture-decision-record) - Templates to record build-or-buy and other key decisions.
- [AWS Generative AI Lens](https://docs.aws.amazon.com/wellarchitected/latest/generative-ai-lens/generative-ai-lens.html) - Well-Architected guidance, including scoping and business alignment.
- [Microsoft Cloud Adoption Framework for AI](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/scenarios/ai/) - Strategy, planning and governance for adopting AI in an organization.

## Free credentials for this domain

From the [tracker](../free-certifications/README.md#ai-strategy-and-leadership):

- OpenAI Academy: *Scope AI Solutions* and *AI Leadership*.
- Microsoft Learn: *Create business value with AI* and *Scale AI in your organization*.
- Salesforce Trailhead: *Change Management for AI Implementation*.
- SAP Learning: *Discovering High-Value Opportunities for Agentic AI*.

## Hands-on lab: use-case portfolio

1. List eight AI use cases for a fictional mid-size insurer (claims, underwriting, customer service, compliance, HR, IT).
2. Score each with the table above in a spreadsheet.
3. For the top two, write a one-page brief: problem, users, baseline, data sources, integration, risks, success criteria.
4. Build the ROI model for the top use case with explicit assumptions.
5. Write an ADR choosing build, buy or extend for it.
6. **Deliverable:** scoring sheet, two briefs, ROI model, one ADR.

## Review questions

1. A business leader asks for "an agent that automatically approves insurance claims" as the first AI project. What should the architect propose?

   <details><summary>Answer</summary>

   Start with an assistive pattern: the AI summarizes claims, extracts fields and flags risks, while a human approves. Measure accuracy and time saved, then automate low-risk claim types once quality is proven.

   </details>

2. Which success criterion is best? (a) "Users like it." (b) "The model is accurate." (c) "Correct and grounded answers on 90% of a 200-question set, and handle time down 30% versus baseline."

   <details><summary>Answer</summary>

   (c). It is specific, measurable and tied to a baseline and a business outcome.

   </details>

3. The workflow lives entirely inside the company's CRM and the requirement is generic email drafting. Build or extend?

   <details><summary>Answer</summary>

   Extend the CRM's built-in agent or copilot features. Custom build adds cost without differentiation.

   </details>

4. In most enterprise AI TCO models, which cost line is usually largest?

   <details><summary>Answer</summary>

   People and operations (build, evaluation, monitoring, support), not token usage.

   </details>

5. Why capture a baseline before the pilot?

   <details><summary>Answer</summary>

   Without it you cannot prove improvement; anecdotes replace evidence and the project struggles to get production funding.

   </details>

6. What is the single most important role to name during discovery?

   <details><summary>Answer</summary>

   The accountable business owner who will adopt the solution and own its outcome after launch.

   </details>
