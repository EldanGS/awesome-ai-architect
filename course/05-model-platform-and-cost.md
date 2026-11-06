# Domain 5: Model Platform, Serving and Cost

**Weight: 12%** · **Time: 8-10 hours** · [Back to course](README.md)

Where the model runs decides latency, cost, data boundaries and operational burden. This domain covers hosted APIs, cloud model platforms, self-hosted inference and FinOps for LLM workloads.

## Learning objectives

- [ ] Compare first-party model APIs, cloud model platforms and self-hosted inference.
- [ ] Estimate monthly cost for a workload from traffic and token assumptions.
- [ ] Apply cost levers: model routing, prompt caching, batching, output limits, distillation.
- [ ] Explain inference serving concepts: throughput, time to first token, batching, quantization, KV cache.
- [ ] Design for rate limits, quotas, provisioned capacity, fallbacks and multi-region resilience.
- [ ] Decide when fine-tuning a smaller model pays off.

## Core concepts

### Deployment options

| Option | Examples | Strengths | Weaknesses |
| --- | --- | --- | --- |
| First-party API | Anthropic API, OpenAI API, Gemini API | Newest models first, simplest. | Data leaves your cloud boundary (under contract), separate billing. |
| Cloud model platform | Amazon Bedrock, Azure AI Foundry, Google Vertex AI | IAM, private networking, regional hosting, consolidated billing, many models. | Model availability and features can lag; quota management per region. |
| Managed open-model hosting | Platform endpoints for open-weight models, inference providers | No GPU operations, open models. | Less control than self-hosting. |
| Self-hosted | vLLM, Text Generation Inference, NVIDIA Triton or NIM, Ollama, on Kubernetes (KServe, Ray Serve) | Full control, air-gap, custom models. | GPU capacity, scaling, patching, safety and on-call are yours. |

### Cost estimation

```text
Monthly cost = requests per month x (input tokens x input price + output tokens x output price)
```

Worked example (use current price lists for real numbers): 1 million requests per month, 3,000 input tokens (system prompt plus retrieved context) and 400 output tokens each. That is 3 billion input and 400 million output tokens per month. With a price of 3 USD per million input tokens and 15 USD per million output tokens, cost is 9,000 + 6,000 = 15,000 USD per month. If 2,000 of the input tokens are a stable system prompt that can be cached at a large discount, input cost drops substantially. If 70% of traffic can go to a model that costs one tenth as much, total cost falls further.

### Cost levers

| Lever | Typical effect | Caveat |
| --- | --- | --- |
| Model routing and cascades | Large savings when most requests are easy. | Needs a classifier and evaluation per route. |
| Prompt caching | Big discount and lower latency on repeated prefixes. | Keep stable content first in the prompt. |
| Batch APIs | Roughly half price for non-urgent jobs. | Results arrive within hours, not seconds. |
| Shorter context | Fewer input tokens. | Requires better retrieval and ranking. |
| Output limits and concise formats | Fewer expensive output tokens. | Do not truncate needed content. |
| Semantic caching of answers | Avoids repeated calls for identical questions. | Risk of stale or wrong reuse; scope by user and permissions. |
| Fine-tuning or distillation to a small model | Lower unit cost at high volume. | Upfront data and evaluation effort, retraining when the base model changes. |
| Provisioned throughput | Predictable latency and capacity. | Pay for reserved capacity even when idle. |

### Inference serving fundamentals

| Term | Meaning | Why the architect cares |
| --- | --- | --- |
| Time to first token (TTFT) | Delay before streaming starts. | Perceived latency for chat. |
| Tokens per second | Generation speed per request. | Total response time. |
| Throughput | Tokens per second across all requests. | Capacity planning and GPU count. |
| Continuous batching | Server merges requests dynamically. | Large throughput gains on self-hosted inference. |
| KV cache | Stored attention state for the prompt. | GPU memory limits concurrency and context length. |
| Quantization (8-bit, 4-bit) | Lower-precision weights. | Fits bigger models on fewer GPUs with small quality loss; must be evaluated. |
| Speculative decoding | Small draft model proposes tokens. | Faster generation at the same quality. |

### Resilience

- Quotas and rate limits exist per model, per region and per account: request increases early.
- Use a gateway with **retries with exponential backoff**, **fallback models** and **circuit breakers**.
- For critical workloads, use **multi-region** or **multi-provider** fallback, and test that prompts work on the fallback model.
- Pin model versions in production; upgrade through evaluation gates.

## Patterns and anti-patterns

**Patterns**

- Cost attribution by application and team via gateway metadata.
- Load testing with realistic prompt and output lengths before launch.
- A model upgrade pipeline: new version runs on the evaluation set and in shadow mode first.

**Anti-patterns**

- Self-hosting a large model "to save money" at low, spiky volume.
- Unpinned model aliases in production that change behavior silently.
- No budget alerts on API keys.

## Reading list

- [vLLM](https://github.com/vllm-project/vllm) - High-throughput inference engine with continuous batching and paged attention.
- [Text Generation Inference](https://github.com/huggingface/text-generation-inference) - Hugging Face's production LLM server.
- [NVIDIA Triton Inference Server](https://github.com/triton-inference-server/server) - Multi-framework inference serving.
- [KServe](https://github.com/kserve/kserve) - Kubernetes-native model serving.
- [Ray](https://github.com/ray-project/ray) - Distributed compute with Ray Serve for model serving.
- [LiteLLM](https://github.com/BerriAI/litellm) - Open-source gateway with a unified API, budgets and fallbacks across providers.
- [Ollama](https://github.com/ollama/ollama) - Run open models locally for prototyping and edge cases.
- [Amazon Bedrock samples](https://github.com/aws-samples/amazon-bedrock-samples) - Examples for Bedrock models, agents and knowledge bases.
- [Anthropic prompt caching docs](https://docs.claude.com/en/docs/build-with-claude/prompt-caching) - How cached prefixes cut cost and latency.
- [FinOps for AI](https://www.finops.org/topic/finops-for-ai/) - FinOps Foundation guidance on managing AI spend.

## Free credentials for this domain

From the [tracker](../free-certifications/README.md#building-llm-applications):

- Anthropic Academy: *Claude with Amazon Bedrock* and *Claude with Google Cloud's Vertex AI*.
- OpenAI Academy: *Optimize AI Application Performance*.
- Salesforce Trailhead: *Model Fine-Tuning*.
- AWS Skill Builder: *AWS MLOps Demonstrated* microcredential.

## Hands-on lab: cost and latency model

1. Pick a workload: an internal RAG assistant with 2,000 users, 15 questions per user per working day.
2. Measure real prompt and output token counts from your Domain 3 lab.
3. Build a spreadsheet: monthly tokens, cost on three models, cost with caching, cost with 70/30 routing.
4. Run a local open model with Ollama or vLLM and measure TTFT and tokens per second.
5. Put LiteLLM (or another gateway) in front of two providers and test fallback by blocking one.
6. **Deliverable:** cost model, latency measurements, and a one-page recommendation.

## Review questions

1. A nightly job classifies 2 million documents and results are needed by the next morning. What is the cheapest design?

   <details><summary>Answer</summary>

   A batch API (or offline batch inference) with a small model validated on an evaluation set. Real-time endpoints are unnecessary.

   </details>

2. Every request starts with the same 5,000-token instruction and policy block. Which lever applies?

   <details><summary>Answer</summary>

   Prompt caching: keep the stable block first so it is served from cache at a discount and lower latency.

   </details>

3. A regulated bank needs Claude models but data must stay within its AWS account boundary and region. Which option fits?

   <details><summary>Answer</summary>

   Use the model through Amazon Bedrock in the required region with private connectivity (VPC endpoints) and IAM, rather than a direct external API.

   </details>

4. Chat users complain the assistant "feels slow" although total response time is acceptable. Which metric and fix?

   <details><summary>Answer</summary>

   Time to first token. Stream responses, shorten or cache the prompt prefix, and pick a lower-latency model or region.

   </details>

5. When does self-hosting an open model become cost-effective?

   <details><summary>Answer</summary>

   At high, steady utilization where GPUs stay busy, or when residency or air-gap requirements force it. At low or spiky volume, APIs are usually cheaper.

   </details>

6. A provider silently updates the model behind an alias and extraction accuracy drops. What should have prevented this?

   <details><summary>Answer</summary>

   Pinning dated model versions in production and promoting new versions only after passing the evaluation set.

   </details>
