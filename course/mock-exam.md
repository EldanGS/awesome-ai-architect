# AI Solution Architect Mock Exam

**60 questions · 120 minutes · pass at 70% (42 correct) and at least 60% per domain** · [Back to course](README.md)

All questions are original scenarios written for this course. Each has one best answer. Take it closed-book, write your answers down, then open the answers.

| Domain | Questions | Count |
| --- | --- | :-: |
| 1. AI and LLM Foundations | 1-6 | 6 |
| 2. Discovery and Business Value | 7-12 | 6 |
| 3. Reference Architectures | 13-24 | 12 |
| 4. Data Architecture | 25-31 | 7 |
| 5. Model Platform and Cost | 32-38 | 7 |
| 6. Evaluation and LLMOps | 39-45 | 7 |
| 7. Security and Responsible AI | 46-54 | 9 |
| 8. Cloud Implementation | 55-60 | 6 |

## Domain 1: AI and LLM Foundations

**1.** A legal team wants a model to answer questions about contracts signed this week. What is the main reason training data alone cannot satisfy this?

- A. Context windows are too small for contracts.
- B. Training data has a cutoff and does not contain new private documents.
- C. Temperature must be zero for legal use.
- D. Models cannot read legal language.

<details><summary>Answer</summary>

**B.** New and private documents must be supplied at request time through retrieval or tools.

</details>

**2.** Which change most directly reduces the cost of a request?

- A. Switching from streaming to non-streaming.
- B. Raising temperature.
- C. Adding more examples to the prompt.
- D. Reducing input and output tokens.

<details><summary>Answer</summary>

**D.** Cost is billed per token. Streaming changes perceived latency, not cost.

</details>

**3.** A team needs a model to classify 40 ticket categories at very high volume with low latency. Which model choice is most appropriate to test first?

- A. A small, fast model validated on a labeled evaluation set.
- B. An image generation model.
- C. The largest reasoning model with extended thinking.
- D. A model with the largest context window.

<details><summary>Answer</summary>

**A.** Classification at volume rarely needs frontier reasoning; prove a small model meets accuracy targets.

</details>

**4.** What must remain the same between indexing documents and embedding user queries?

- A. The embedding model.
- B. The chunk overlap.
- C. The temperature.
- D. The LLM used for generation.

<details><summary>Answer</summary>

**A.** Vectors from different embedding models are not comparable.

</details>

**5.** A team wants the model to "learn" 5,000 frequently changing product facts. Which approach is generally best?

- A. Retrieval over a product database or documents.
- B. Use a higher temperature.
- C. Increase max output tokens.
- D. Fine-tune monthly.

<details><summary>Answer</summary>

**A.** Retrieval keeps facts current and citable; fine-tuning is better for behavior and style.

</details>

**6.** When is enabling a model's extended reasoning mode most justified?

- A. For short greetings in a chatbot.
- B. For every request, to maximize quality.
- C. To reduce cost.
- D. For multi-step analytical tasks where evaluation shows a meaningful accuracy gain worth the extra latency and tokens.

<details><summary>Answer</summary>

**D.** Reasoning modes cost more tokens and time; use them where measured gains justify it.

</details>

## Domain 2: Discovery and Business Value

**7.** In discovery, which item should be captured before any pilot begins?

- A. The final model name.
- B. A measured baseline of the current process.
- C. The fine-tuning dataset size.
- D. The UI color scheme.

<details><summary>Answer</summary>

**B.** Without a baseline, improvement cannot be proven.

</details>

**8.** Which is the best first AI use case for a risk-averse hospital administration?

- A. Replacing triage nurses with a chatbot.
- B. Autonomous diagnosis without clinician review.
- C. Drafting discharge summary text that a clinician reviews and signs.
- D. Automatically changing medication orders.

<details><summary>Answer</summary>

**C.** High value with a human reviewing every output keeps risk low while proving value.

</details>

**9.** A use case scores high on value but data lives in scanned paper forms with no owner. What should the architect recommend?

- A. Increase the budget for tokens.
- B. Start building the agent immediately.
- C. Address data readiness first: digitization, ownership and access, or pick a more ready use case for the first pilot.
- D. Fine-tune a model on the paper forms.

<details><summary>Answer</summary>

**C.** Data readiness is a gating factor; without owned, accessible data the project stalls.

</details>

**10.** The requirement is generic meeting summarization for all employees using the existing office suite. What is usually the best option?

- A. Buy or enable the suite's built-in assistant.
- B. Self-host an open model.
- C. Train a model from scratch.
- D. Build a custom app on a model API.

<details><summary>Answer</summary>

**A.** Generic productivity is best served by off-the-shelf tools integrated with the suite.

</details>

**11.** Which success criterion is best defined?

- A. "Users will be happier."
- B. "First-contact resolution rises from 62% to 70% for the pilot group within 8 weeks, with no drop in satisfaction."
- C. "We will use the best model."
- D. "The assistant should be smart."

<details><summary>Answer</summary>

**B.** It is specific, baselined, time-bound and tied to a business outcome.

</details>

**12.** A pilot succeeded technically but usage dropped after two weeks. What was most likely neglected?

- A. Embedding dimension.
- B. Change management: training, workflow integration and feedback loops.
- C. Quantization.
- D. Batch inference.

<details><summary>Answer</summary>

**B.** Adoption depends on fitting the workflow and supporting users, not only model quality.

</details>

## Domain 3: Reference Architectures

**13.** Requirement: translate product descriptions into 12 languages with a fixed style guide. Which pattern?

- A. RAG over the internet.
- B. Multi-agent system with a planner.
- C. Fine-tune 12 models.
- D. Direct prompting (optionally parallelized per language).

<details><summary>Answer</summary>

**D.** Known transformation; parallel prompts per language are enough.

</details>

**14.** Which statement best distinguishes a workflow from an agent?

- A. Workflows use LLMs; agents do not.
- B. Agents cannot use tools.
- C. In a workflow, code defines the path; in an agent, the model decides next steps and tool calls in a loop.
- D. Workflows require fine-tuning.

<details><summary>Answer</summary>

**C.** Control of the execution path is the key difference.

</details>

**15.** A support bot must handle billing, technical and sales questions with different prompts and knowledge bases. Which building block fits?

- A. Routing.
- B. Speculative decoding.
- C. Fine-tuning.
- D. Evaluator-optimizer.

<details><summary>Answer</summary>

**A.** Classify the request, then send it to the specialized path.

</details>

**16.** An agent occasionally loops calling a failing API until the session times out, generating large bills. Which control is missing?

- A. A larger context window.
- B. More tools.
- C. Higher temperature.
- D. Step, token and time budgets with error handling.

<details><summary>Answer</summary>

**D.** Budgets and failure handling bound runaway loops.

</details>

**17.** In MCP terms, what exposes tools, resources and prompts to an AI application?

- A. An embedding model.
- B. An MCP client.
- C. An MCP server.
- D. A vector database.

<details><summary>Answer</summary>

**C.** Servers expose capabilities; clients inside the host application connect to them.

</details>

**18.** A remote MCP server lets an agent read employees' calendars. How should it authenticate?

- A. No authentication inside the corporate network.
- B. One shared admin token for all users.
- C. The user's password pasted into the prompt.
- D. Delegated, user-scoped authorization (for example OAuth) so the agent acts with each user's permissions.

<details><summary>Answer</summary>

**D.** Delegated, scoped access limits blast radius and preserves per-user permissions.

</details>

**19.** Where should human approval be placed in an agent that researches vendors and then issues purchase orders?

- A. Before the irreversible purchase order action.
- B. Nowhere; agents should be autonomous.
- C. Only after the purchase order is sent.
- D. Before every search query.

<details><summary>Answer</summary>

**A.** Approve at the point of irreversible, high-impact action.

</details>

**20.** A research task needs to read 200 documents and synthesize findings. Which design best balances speed and quality?

- A. Orchestrator-workers: parallel workers summarize subsets, an orchestrator synthesizes.
- B. Keyword search only.
- C. One prompt containing all 200 documents regardless of size.
- D. Fine-tune on the 200 documents.

<details><summary>Answer</summary>

**A.** Parallel workers with separate contexts scale better and keep each context focused.

</details>

**21.** What is the main benefit of placing an AI gateway in front of all model calls?

- A. It trains models faster.
- B. It eliminates prompt injection.
- C. Central keys, quotas, routing, fallback, caching, logging and cost attribution.
- D. It removes the need for evaluation.

<details><summary>Answer</summary>

**C.** It is a control plane for model access; it does not remove other controls.

</details>

**22.** An onboarding process runs over five days with waits for document uploads. Which capability must the agent platform provide?

- A. Larger embeddings.
- B. Lower temperature.
- C. Streaming tokens.
- D. Durable execution with persisted state and resume.

<details><summary>Answer</summary>

**D.** Long-running processes need checkpointing and resume across restarts.

</details>

**23.** Which component lets a chat assistant remember a user's preferred report format across sessions?

- A. A re-ranker.
- B. Short-term message history only.
- C. Long-term memory store with consent and deletion support.
- D. The system prompt for all users.

<details><summary>Answer</summary>

**C.** Cross-session facts need long-term memory governed for privacy.

</details>

**24.** An architect proposes five cooperating agents for a task that a single structured prompt passes at 97%. What is the best response?

- A. Fine-tune each agent.
- B. Add a sixth agent for verification.
- C. Prefer the single prompt; multi-agent adds cost and complexity without measured benefit.
- D. Approve; more agents are more robust.

<details><summary>Answer</summary>

**C.** Use the simplest pattern that meets the requirement.

</details>

## Domain 4: Data Architecture

**25.** Retrieval misses answers that are split across a heading and the paragraph below it. Which chunking fix fits best?

- A. Structure-aware chunking that keeps headings with their sections.
- B. Smaller fixed-size chunks with no overlap.
- C. Larger temperature.
- D. Remove headings.

<details><summary>Answer</summary>

**A.** Respecting document structure keeps related content together.

</details>

**26.** Users search for SKU codes and acronyms; dense retrieval performs poorly. What is the standard fix?

- A. Lower chunk overlap.
- B. Hybrid search combining keyword (BM25) and vector retrieval.
- C. A bigger LLM.
- D. More output tokens.

<details><summary>Answer</summary>

**B.** Keyword search handles exact tokens that embeddings blur.

</details>

**27.** A sales VP asks "What was revenue by region last quarter?" through the assistant. What should handle it?

- A. The model's training data.
- B. A governed SQL or semantic-layer tool over the warehouse, with the user's permissions.
- C. Vector search over slide decks.
- D. A summarization prompt.

<details><summary>Answer</summary>

**B.** Aggregations need structured queries, not similar text.

</details>

**28.** A RAG system quotes a policy that was deleted from the source last week. What fixes the root cause?

- A. Prompt telling the model to ignore old content.
- B. A stronger LLM.
- C. Smaller chunks.
- D. Incremental sync with lineage that deletes chunks when sources are removed.

<details><summary>Answer</summary>

**D.** Lineage and deletion propagation keep the index consistent with sources.

</details>

**29.** Where should document-level permissions be enforced in an enterprise RAG system?

- A. After the model answers, by asking it to remove restricted content.
- B. In retrieval, by filtering on access metadata using the user's identity before results reach the model.
- C. In the system prompt.
- D. In the front-end CSS.

<details><summary>Answer</summary>

**B.** The model must never receive content the user cannot access.

</details>

**30.** Which technique improves retrieval of chunks that are ambiguous on their own (for example "Revenue grew 3%")?

- A. Disabling re-ranking.
- B. Shorter queries.
- C. Removing metadata.
- D. Contextual chunking: prepend document-level context to each chunk before embedding.

<details><summary>Answer</summary>

**D.** Adding context makes each chunk self-describing for search.

</details>

**31.** Questions require multi-hop reasoning over relationships between companies, subsidiaries and directors. Which retrieval approach is strongest?

- A. Larger chunks.
- B. Knowledge graph or GraphRAG.
- C. Keyword search only.
- D. Caching.

<details><summary>Answer</summary>

**B.** Graphs model relationships explicitly for multi-hop traversal.

</details>

## Domain 5: Model Platform and Cost

**32.** A workload sends a 6,000-token fixed instruction block with every request. Which lever gives the largest immediate saving?

- A. Raising max output tokens.
- B. Disabling streaming.
- C. Using a larger model.
- D. Prompt caching of the stable prefix.

<details><summary>Answer</summary>

**D.** Cached prefixes are billed at a discount and cut latency.

</details>

**33.** A monthly report generation job over 500,000 records is not time-sensitive. Which option is cheapest?

- A. Batch inference API.
- B. Self-hosting on reserved GPUs for the month.
- C. Running it from user browsers.
- D. Real-time API with provisioned throughput.

<details><summary>Answer</summary>

**A.** Batch APIs trade latency for a large discount.

</details>

**34.** A ministry requires a fully air-gapped deployment with no external network. Which option fits?

- A. Self-hosted open-weight model on on-premises GPUs.
- B. First-party model API.
- C. A browser plugin.
- D. Cloud model platform over the internet.

<details><summary>Answer</summary>

**A.** Air-gap rules out external APIs.

</details>

**35.** Users say the chat feels slow, though total response time is under 6 seconds. Which metric matters most?

- A. Throughput per GPU.
- B. Index size.
- C. Time to first token.
- D. Embedding dimension.

<details><summary>Answer</summary>

**C.** Perceived latency in chat is dominated by time to first token; streaming helps.

</details>

**36.** Which technique lets a self-hosted model fit on fewer GPUs at a small quality cost?

- A. Higher temperature.
- B. Routing.
- C. Quantization.
- D. Prompt chaining.

<details><summary>Answer</summary>

**C.** Lower-precision weights reduce memory needs.

</details>

**37.** An app's provider has a regional outage. What design would have kept it running?

- A. Increasing chunk size.
- B. Gateway fallback to another region or provider, with prompts tested on the fallback model.
- C. Disabling logs.
- D. Pinning a model alias.

<details><summary>Answer</summary>

**B.** Fallback paths must exist and be tested in advance.

</details>

**38.** 75% of requests are simple FAQs; 25% need deep reasoning. Which architecture lowers cost while keeping quality?

- A. Send everything to the largest model.
- B. Send everything to the smallest model.
- C. A router or cascade: small model for simple requests, large model for complex ones, validated per route.
- D. Disable retrieval.

<details><summary>Answer</summary>

**C.** Routing matches model cost to request difficulty.

</details>

## Domain 6: Evaluation and LLMOps

**39.** What should be the release gate for a prompt change in a production RAG app?

- A. No gate; prompts are not code.
- B. The author tries three questions manually.
- C. An automated evaluation suite in CI with thresholds on key metrics.
- D. The model provider's benchmark scores.

<details><summary>Answer</summary>

**C.** Prompt changes need the same rigor as code changes.

</details>

**40.** An LLM judge is used to grade faithfulness. How do you know it is trustworthy?

- A. It always gives high scores.
- B. Measure agreement with human-labeled examples and recalibrate the rubric as needed.
- C. It runs fast.
- D. It uses the largest model.

<details><summary>Answer</summary>

**B.** Judges must be calibrated against humans.

</details>

**41.** Answers are wrong, and traces show the correct passage was never retrieved. Which component should be improved first?

- A. The UI.
- B. Retrieval (chunking, hybrid search, re-ranking, filters).
- C. The generation prompt.
- D. The output token limit.

<details><summary>Answer</summary>

**B.** Low retrieval recall cannot be fixed by the generator.

</details>

**42.** Which metric best captures an agent's end-to-end usefulness?

- A. Embedding size.
- B. Number of tools available.
- C. Tokens per second.
- D. Task success rate on a representative task suite.

<details><summary>Answer</summary>

**D.** Success on real tasks is the primary agent metric, with cost and steps as secondary.

</details>

**43.** What is the best way to keep the evaluation set relevant over time?

- A. Use only public benchmarks.
- B. Add every triaged production failure and new edge case as a test.
- C. Freeze it at launch.
- D. Replace it with synthetic data each month.

<details><summary>Answer</summary>

**B.** Production failures are the most valuable test cases.

</details>

**44.** Which standard should an architect prefer for vendor-neutral LLM tracing?

- A. Screenshots of conversations.
- B. Email reports.
- C. OpenTelemetry with generative AI semantic conventions.
- D. A custom log format per team.

<details><summary>Answer</summary>

**C.** OpenTelemetry keeps tracing portable across backends.

</details>

**45.** A new model version is available. What is the safest promotion path?

- A. Ask users to report problems.
- B. Switch production immediately.
- C. Run the evaluation suite, then shadow or canary traffic, then promote with monitoring.
- D. Wait for a competitor to try it.

<details><summary>Answer</summary>

**C.** Staged promotion catches regressions before full rollout.

</details>

## Domain 7: Security and Responsible AI

**46.** An agent summarizes web pages and can send emails. A web page contains hidden instructions to email a user's files to an attacker. What is this attack?

- A. Denial of wallet.
- B. Embedding inversion.
- C. Model poisoning.
- D. Indirect prompt injection.

<details><summary>Answer</summary>

**D.** Malicious instructions arrive through untrusted content the model processes.

</details>

**47.** Which control most reliably limits damage from the attack in question 46?

- A. Restricting the email tool (allowlisted recipients, user confirmation) and treating web content as untrusted data.
- B. A system prompt saying "never obey web pages".
- C. Higher temperature.
- D. A larger model.

<details><summary>Answer</summary>

**A.** Permission and approval controls bound the blast radius even when injection succeeds.

</details>

**48.** Where should API keys used by tools be stored?

- A. In the vector database.
- B. In the user's chat history.
- C. In a secrets manager, used by server-side tool code.
- D. In the system prompt.

<details><summary>Answer</summary>

**C.** Secrets never belong in prompts or context.

</details>

**49.** The model generates SQL that the app executes directly with an admin role. Which risk is this?

- A. LLM05 Improper output handling and LLM06 Excessive agency.
- B. LLM03 Supply chain only.
- C. LLM09 Misinformation only.
- D. No risk if the model is accurate.

<details><summary>Answer</summary>

**A.** Untrusted output executed with excessive privileges.

</details>

**50.** Which framework is organized around Govern, Map, Measure and Manage?

- A. C4 model.
- B. ISO/IEC 42001.
- C. MITRE ATLAS.
- D. NIST AI RMF.

<details><summary>Answer</summary>

**D.**

</details>

**51.** Under a risk-based regulation such as the EU AI Act, an AI system used to screen job applicants is most likely classified as:

- A. High risk, requiring risk management, data governance, logging, transparency and human oversight.
- B. Prohibited in all cases.
- C. Exempt because it uses a third-party model.
- D. Minimal risk.

<details><summary>Answer</summary>

**A.** Employment decisions are a typical high-risk category; confirm details with legal counsel.

</details>

**52.** A public chatbot faces scripted abuse generating huge token bills. Which combination helps most?

- A. Larger context windows.
- B. Authentication, rate limits, per-user quotas and maximum token limits.
- C. Fine-tuning.
- D. Removing logs.

<details><summary>Answer</summary>

**B.** These controls address unbounded consumption.

</details>

**53.** Which practice best addresses supply-chain risk for MCP servers and model weights?

- A. Allowlist reviewed sources, pin versions, verify signatures and scan dependencies.
- B. Run everything as root for compatibility.
- C. Install any popular server from the internet.
- D. Let each developer choose freely.

<details><summary>Answer</summary>

**A.**

</details>

**54.** Which UX feature supports both transparency and reduced over-reliance?

- A. Always answering confidently.
- B. Hiding that responses are AI-generated.
- C. Removing feedback buttons.
- D. Showing sources and indicating when the system is uncertain or cannot answer.

<details><summary>Answer</summary>

**D.**

</details>

## Domain 8: Cloud Implementation

**55.** On AWS, which service provides managed access to multiple foundation models with IAM and private connectivity?

- A. AWS Direct Connect alone.
- B. Amazon Bedrock.
- C. Amazon Route 53.
- D. Amazon S3 Glacier.

<details><summary>Answer</summary>

**B.**

</details>

**56.** On Azure, which service is commonly placed in front of model endpoints to enforce token quotas, load balancing and logging across apps?

- A. Azure DNS.
- B. Azure API Management with AI gateway policies.
- C. Azure Blob Storage.
- D. Azure Virtual Desktop.

<details><summary>Answer</summary>

**B.**

</details>

**57.** On Google Cloud, which feature provides private access to managed services from a VPC?

- A. Cloud CDN.
- B. Cloud Scheduler.
- C. Private Service Connect.
- D. Firebase Hosting.

<details><summary>Answer</summary>

**C.**

</details>

**58.** Forty teams want to build AI apps. What should the central platform team provide first?

- A. GPUs for every team.
- B. A single shared chatbot for all use cases.
- C. Separate unmanaged API keys for each developer.
- D. An AI landing zone: shared gateway, approved models, guardrails, networking patterns and observability.

<details><summary>Answer</summary>

**D.** A landing zone lets many teams scale safely and consistently.

</details>

**59.** During design, which check prevents a launch-day surprise in a new region?

- A. Deploy to all regions.
- B. Choose the cheapest region at launch time.
- C. Rely on default quotas.
- D. Confirm model availability and quota in the target region early.

<details><summary>Answer</summary>

**D.**

</details>

**60.** Which artifact best captures why the team chose a managed vector store over self-hosting?

- A. An architecture decision record.
- B. A slide with a logo.
- C. A chat message.
- D. A code comment in the front end.

<details><summary>Answer</summary>

**A.**

</details>

## Scoring

Count correct answers per domain using the table at the top. If any domain is below 60%, re-study that domain, redo its lab and retake the exam after a few days.
