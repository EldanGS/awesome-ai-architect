# Domain 1: AI and LLM Foundations for Architects

**Weight: 10%** · **Time: 8-10 hours** · [Back to course](README.md)

An architect does not need to train models, but must predict how they behave in production: where they excel, how they fail, and which knobs change cost, latency and quality.

## Learning objectives

- [ ] Explain tokens, context windows, sampling and why the same prompt can give different outputs.
- [ ] Compare frontier, mid-tier, small and open-weight models on quality, latency, cost and deployment options.
- [ ] Describe embeddings and why they power search, clustering and RAG.
- [ ] Name the main failure modes of LLMs and the architectural control for each.
- [ ] Explain reasoning (extended thinking) models and when their extra cost is justified.
- [ ] Choose between prompting, RAG, fine-tuning and tool use for a given requirement.

## Core concepts

### How an LLM request works

1. Input text is split into **tokens** (roughly 3-4 characters of English each). Pricing, limits and latency are all counted in tokens.
2. The model reads the whole **context window**: system prompt, conversation history, retrieved documents, tool definitions and tool results.
3. It generates output one token at a time. **Temperature** and **top-p** control randomness. Low values give more repeatable output; they do not make answers correct.
4. Generation stops at a stop sequence, a maximum token limit, or when the model calls a tool.

Architectural consequences:

| Fact | Consequence for design |
| --- | --- |
| Cost scales with input plus output tokens. | Long system prompts and large retrieved contexts dominate cost; cache them where the provider supports prompt caching. |
| Output tokens are slower and pricier than input tokens. | Ask for concise, structured output; stream long answers. |
| Context windows are large but not free. | Quality can drop when relevant facts sit in the middle of very long contexts; retrieve less, rank better. |
| Models are stateless between calls. | Conversation memory is your responsibility: store, summarize, and re-send it. |
| Outputs are probabilistic. | Validate structure (JSON schema), test with evaluation sets, and never assume one passing run means it works. |

### Model families and how to choose

| Tier | Typical use | Trade-off |
| --- | --- | --- |
| Frontier models (largest Claude, GPT and Gemini models) | Complex reasoning, coding, agents, long documents. | Highest quality, highest cost and latency. |
| Mid-tier models | Most production chat, RAG and extraction workloads. | Best quality per dollar for many tasks. |
| Small and fast models | Classification, routing, guardrails, autocomplete. | Cheap and fast; weaker on multi-step reasoning. |
| Open-weight models (Llama, Mistral, Qwen, Gemma and others) | Data residency, air-gapped or on-prem, fine-tuning, cost control at very high volume. | You own serving, scaling, patching and safety tuning. |
| Embedding models | Semantic search, deduplication, clustering. | Must use the same model for indexing and querying. |
| Reasoning modes | Hard math, planning, code and multi-step analysis. | More tokens and seconds per answer; enable only where accuracy gains are measured. |

Rule of thumb: **prototype with the strongest model, then step down** to the cheapest model that still passes your evaluation set. Use a router to send easy requests to small models.

### Embeddings

An embedding model maps text (or images) to a vector so that similar meanings land close together. Architects use embeddings for semantic search, RAG retrieval, recommendation, duplicate detection and clustering. Key decisions: embedding dimension (storage cost), multilingual support, maximum input length, and a re-indexing plan when you change models.

### Failure modes and controls

| Failure mode | Example | Primary controls |
| --- | --- | --- |
| Hallucination | Invents a policy clause. | Ground with RAG, require citations, allow "I don't know", evaluate faithfulness. |
| Stale knowledge | Unaware of last month's price change. | Retrieval or tools for live data; never rely on training data for facts that change. |
| Prompt injection | A retrieved web page tells the agent to email data out. | Treat retrieved content as untrusted, least-privilege tools, human approval for risky actions. |
| Inconsistent formatting | Breaks a downstream JSON parser. | Structured outputs or tool calls with schemas; validate and retry. |
| Bias and unsafe content | Uneven quality across user groups. | Evaluation slices, content filters, human review, responsible AI review. |
| Over-reliance | Users trust wrong answers. | UX that shows sources and confidence, escalation paths, user training. |

### Prompting vs RAG vs tools vs fine-tuning

| Need | Best first choice | Why |
| --- | --- | --- |
| Change tone, format or task instructions | Prompting | Cheapest, fastest to iterate. |
| Answer from private or changing documents | RAG | Keeps facts outside the model, supports citations and access control. |
| Act on live systems or fetch real-time data | Tool use (function calling, MCP) | Model decides; your code executes with your permissions. |
| Consistent style or narrow task at high volume | Fine-tuning a smaller model | Lower cost per call after enough examples; needs data and an evaluation set. |
| New knowledge the model must "know" | Usually RAG, not fine-tuning | Fine-tuning teaches behavior better than facts. |

## Patterns and anti-patterns

**Patterns**

- Model abstraction layer (gateway) so you can switch providers and models without rewriting applications.
- Evaluation set first: write 30-100 representative test cases before arguing about which model is best.
- Cascade: small model first, escalate to a larger one on low confidence.

**Anti-patterns**

- Choosing a model from a leaderboard instead of your own evaluation data.
- Fine-tuning to fix a retrieval problem.
- Treating temperature 0 as a correctness guarantee.

## Reading list

- [Prompt Engineering Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) - Broad reference on prompting techniques, model behavior and LLM limitations.
- [Generative AI for Beginners](https://github.com/microsoft/generative-ai-for-beginners) - Microsoft's 21-lesson course; lessons 1-6 cover the foundations for this domain.
- [LLM Course](https://github.com/mlabonne/llm-course) - Roadmap from LLM fundamentals to engineering, with notebooks.
- [Anthropic courses](https://github.com/anthropics/courses) - Free courses on the Claude API, prompt engineering and tool use.
- [OpenAI Cookbook](https://github.com/openai/openai-cookbook) - Practical examples of embeddings, structured outputs and tool calling.
- [Introduction to Large Language Models](https://www.skills.google/course_templates/539) - Google's short course on how LLMs work, with a free badge.
- [AI Engineering resources](https://github.com/chiphuyen/aie-book) - Companion repository to Chip Huyen's *AI Engineering* book.

## Free credentials for this domain

Earn these from the [Free AI Certifications Tracker](../free-certifications/README.md#ai-and-generative-ai-foundations):

- Anthropic Academy: *AI Fluency: Framework and foundations* and *AI capabilities and limitations*.
- Google Skills: *Introduction to Generative AI* and *Introduction to Large Language Models*.
- Microsoft Learn: *Introduction to AI concepts* and *Explore Generative AI*.
- OpenAI Academy: *AI Foundations*.

## Hands-on lab: model selection experiment

**Goal:** choose a model with data, not opinion.

1. Pick a task: for example, extract `vendor`, `amount`, `due_date` from 20 sample invoices (write them yourself or generate synthetic ones).
2. Write the expected output for each sample. This is your evaluation set.
3. Call three models of different tiers through their APIs (free tiers or credits are enough). Use the same prompt and a JSON schema.
4. Record accuracy per field, median latency, and cost per 1,000 requests from the published price lists.
5. Repeat with temperature 0 and 1 and note the variance.
6. **Deliverable:** a one-page decision record: which model you choose, why, and the cheapest model that meets a 95% field accuracy target.

## Review questions

1. A support assistant must answer from a 4,000-page product manual that changes weekly. Which approach should the architect choose first?

   <details><summary>Answer</summary>

   RAG over the manual with a scheduled re-index. Fine-tuning would be stale after each change and cannot cite sources.

   </details>

2. Why does doubling the retrieved context from 8 to 16 chunks often raise cost without improving answers?

   <details><summary>Answer</summary>

   Input tokens double, and extra low-relevance chunks dilute attention. Better ranking (re-ranking, metadata filters) usually beats more chunks.

   </details>

3. A team sets temperature to 0 and declares the system "deterministic and accurate". What is wrong?

   <details><summary>Answer</summary>

   Low temperature reduces variance but does not guarantee identical outputs across model versions or infrastructure, and it does nothing for correctness. Accuracy needs grounding and evaluation.

   </details>

4. When is an open-weight model the better architectural choice than a hosted frontier API?

   <details><summary>Answer</summary>

   When data must stay on-prem or air-gapped, when regulation forbids third-party processing, when you need deep customization, or at very high steady volume where self-hosting is cheaper. The team must accept serving and safety operations.

   </details>

5. You change the embedding model in a RAG system. What else must change?

   <details><summary>Answer</summary>

   Re-embed and re-index the whole corpus. Query and document vectors must come from the same model; mixing them breaks similarity search.

   </details>

6. Name the control for each: hallucinated facts, broken JSON, a malicious instruction inside a retrieved document.

   <details><summary>Answer</summary>

   Grounding with citations and faithfulness evaluation; structured outputs with schema validation and retry; treating retrieved content as untrusted data with least-privilege tools and human approval for risky actions.

   </details>
