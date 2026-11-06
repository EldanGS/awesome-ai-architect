# Awesome AI Architect [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

<!--lint disable awesome-git-repo-age-->

> A curated list of courses, reference architectures, repositories, frameworks and certifications to prepare for the **AI Solution Architect** role: designing grounded, agentic, secure and cost-aware AI systems that enterprises can run in production.

This list is more than links. It ships with a complete, free **certification prep course** and a **Free AI Certifications Tracker** that gathers 230+ free AI courses with free certificates or badges from Anthropic, OpenAI, Google, Microsoft, NVIDIA, Hugging Face, LangChain, Salesforce, Databricks, MongoDB, Neo4j and more, in one place.

**Start here:**

- [AI Solution Architect Certification Prep Course](course/README.md) - 8 weighted domains, labs, review questions, a 60-question mock exam and a design-review capstone.
- [Free AI Certifications Tracker](free-certifications/README.md) - 132 free credentials from FAANG, Big Tech and frontier AI labs, ordered as a 10-week study path, with checkboxes to track your progress.
- [Free and paid certifications](certifications.md) - Free credentials, paid certificate programs and proctored AWS, Microsoft, Google Cloud, NVIDIA, Databricks and Anthropic exams for AI architects, with exam facts and retirement notes.

## Contents

- [Free Courses from Top AI Companies](#free-courses-from-top-ai-companies)
  - [Google, DeepMind and Kaggle](#google-deepmind-and-kaggle)
  - [Meta](#meta)
  - [Amazon and AWS](#amazon-and-aws)
  - [Apple](#apple)
  - [Netflix](#netflix)
  - [Microsoft](#microsoft)
  - [NVIDIA](#nvidia)
  - [OpenAI](#openai)
  - [Anthropic](#anthropic)
  - [Oracle](#oracle)
- [Courses and Learning Paths](#courses-and-learning-paths)
  - [Free Courses with Certificates](#free-courses-with-certificates)
  - [GitHub Curricula](#github-curricula)
- [Architecture Patterns and Guides](#architecture-patterns-and-guides)
- [Cloud Reference Architectures](#cloud-reference-architectures)
  - [AWS](#aws)
  - [Microsoft Azure](#microsoft-azure)
  - [Google Cloud](#google-cloud)
- [System Design](#system-design)
- [Agent Frameworks](#agent-frameworks)
- [Agent Protocols](#agent-protocols)
- [RAG and Vector Databases](#rag-and-vector-databases)
- [AI Gateways and Routing](#ai-gateways-and-routing)
- [Inference Serving](#inference-serving)
- [Evaluation](#evaluation)
- [Observability and LLMOps](#observability-and-llmops)
- [Cost and FinOps](#cost-and-finops)
- [Security and Guardrails](#security-and-guardrails)
  - [Frameworks and Standards](#frameworks-and-standards)
  - [Guardrails and Red Teaming](#guardrails-and-red-teaming)
  - [Threat Modeling](#threat-modeling)
- [Responsible AI and Governance](#responsible-ai-and-governance)
- [Architecture Documentation](#architecture-documentation)
- [Cookbooks and Example Apps](#cookbooks-and-example-apps)
- [Interview Preparation](#interview-preparation)
- [Related Awesome Lists](#related-awesome-lists)

## Free Courses from Top AI Companies

Free courses, learning paths and official tutorials from FAANG, Big Tech and the frontier AI labs only. Items marked *Free badge* or *Free certificate* award a credential at no cost; the rest are free to learn. Paid programs are in [certifications](certifications.md#paid-certificate-programs).

### Google, DeepMind and Kaggle

- [Google Skills catalog](https://www.skills.google/catalog) - Google's renamed Cloud Skills Boost catalog of on-demand courses, labs, learning paths, and skill badges, with many AI items free to start. Free badge.
- [Introduction to Machine Learning Problem Framing](https://developers.google.com/machine-learning/problem-framing) - Short course on deciding whether a problem needs ML and translating a business need into a well-defined ML task.
- [Rules of Machine Learning](https://developers.google.com/machine-learning/guides/rules-of-ml) - Classic engineering guide of practical best practices for building and operating production ML systems.
- [Beginner: Introduction to Generative AI learning path](https://www.skills.google/paths/118) - Free microlearning path covering generative AI, LLMs, and responsible AI fundamentals on Google Skills. Free badge.
- [Introduction to Large Language Models](https://www.skills.google/course_templates/539) - Short course explaining what LLMs are, where they fit, and how prompt tuning improves their output. Free badge.
- [Machine Learning Operations (MLOps) for Generative AI](https://www.skills.google/course_templates/927) - Covers the operational challenges of deploying and managing generative models and the Vertex/Agent Platform tooling that addresses them. Free badge.
- [Vector Search and Embeddings](https://www.skills.google/course_templates/939) - Hands-on look at embeddings, semantic and hybrid search, and retrieval-augmented generation using Google's vector search service. Free badge.
- [Machine Learning Operations (MLOps): Getting Started](https://www.skills.google/course_templates/158) - Introduces MLOps tools and practices for deploying, evaluating, monitoring, and operating ML systems on Google Cloud. Free badge.
- [Responsible AI: Applying AI Principles with Google Cloud](https://www.skills.google/course_templates/388) - Explains how Google operationalizes responsible AI and offers a framework teams can adapt for their own governance. Free badge.
- [Google Cloud Machine Learning & AI training hub](https://cloud.google.com/learn/training/machinelearning-ai) - Landing page that maps Google Cloud AI and ML courses and paths by role and experience level.
- [Generative AI on Google Cloud samples](https://github.com/GoogleCloudPlatform/generative-ai) - Large official repository of notebooks and sample apps for RAG, agents, evaluation, and Gemini on Google Cloud.
- [5-Day Gen AI Intensive Course with Google](https://www.kaggle.com/learn-guide/5-day-genai) - Self-paced version of Google's intensive on foundation models, prompting, embeddings, agents, and MLOps for gen AI with codelabs and whitepapers.
- [5-Day AI Agents Intensive Course with Google](https://www.kaggle.com/learn-guide/5-day-agents) - Self-paced intensive on agent architecture, tools, memory, evaluation, and production deployment with hands-on labs.

### Meta

- [Getting Started with Fully Sharded Data Parallel (FSDP2)](https://docs.pytorch.org/tutorials/intermediate/FSDP_tutorial.html) - Hands-on tutorial on sharding large-model training across GPUs with PyTorch FSDP2.
- [Meta AI developer hub (Llama docs)](https://dev.meta.ai/) - Meta's developer portal for Llama models and tools, which the former llama.com docs now redirect to.

### Amazon and AWS

- [AWS Skill Builder](https://skillbuilder.aws/) - AWS's learning platform with a large free tier of digital courses, learning plans, and free microcredential labs. Free badge.
- [AWS AI courses and training hub](https://aws.amazon.com/ai/learn/) - Entry point to AWS's AI and generative AI training by role, including free Skill Builder content.
- [Amazon Bedrock AgentCore samples](https://github.com/awslabs/agentcore-samples) - Official samples for taking agents to production with AgentCore runtime, gateway, memory, and identity (repo renamed from amazon-bedrock-agentcore-samples).

### Apple

- [Apple Developer: AI & Machine Learning](https://developer.apple.com/machine-learning/) - Apple's hub for on-device ML frameworks, tools, models, and WWDC sessions.

### Netflix

- [Metaflow tutorials](https://docs.metaflow.org/getting-started/tutorials) - Official tutorials for Netflix's open-source framework for building and operating ML and AI workflows.

### Microsoft

- [Microsoft Learn training](https://learn.microsoft.com/en-us/training/) - Microsoft's free catalog of modules, learning paths, and career paths with sandbox labs. Free badge.
- [Microsoft Learn AI learning hub](https://learn.microsoft.com/en-us/ai/) - Curated AI learning journeys for building and deploying AI apps and agents on Microsoft platforms.
- [Training for solutions architects (career path)](https://learn.microsoft.com/en-us/training/career-paths/solution-architect) - Role-based Learn paths for designing secure, scalable Azure solution architectures. Free badge.
- [Azure Architecture Center: Get started with AI architecture design](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/ai-get-started) - Architecture guidance and reference designs for AI and ML workloads on Azure.
- [AI Agents for Beginners](https://github.com/microsoft/ai-agents-for-beginners) - Lesson series on agent design patterns, tool use, multi-agent systems, and production concerns.

### NVIDIA

- [NVIDIA DLI self-paced training](https://www.nvidia.com/en-us/training/self-paced-courses/) - Catalog of NVIDIA Deep Learning Institute online courses, including a set of free introductory ones.
- [Generative AI Explained (DLI)](https://learn.nvidia.com/courses/course-detail?course_id=course-v1:DLI+S-FX-07+V1) - Free no-code DLI course on how generative AI works, its applications, and its challenges (detail page is JS-rendered).
- [NVIDIA Generative AI Examples](https://github.com/NVIDIA/GenerativeAIExamples) - Official reference implementations for RAG, agents, and NIM-based gen AI pipelines.

### OpenAI

- [OpenAI API documentation](https://developers.openai.com/api/docs) - Official guides for the OpenAI platform covering models, tools, agents, and evaluation.

### Anthropic

- [Claude Academy](https://academy.claude.com/) - Anthropic's renamed learning hub for working and building with Claude, hosting AI Fluency and capabilities courses. Free certificate.
- [Anthropic courses catalog (Skilljar)](https://anthropic.skilljar.com/) - Full catalog of free Anthropic courses on Claude, Claude Code, the API, MCP, and agents with completion certificates. Free certificate.
- [Model Context Protocol: Advanced Topics](https://anthropic.skilljar.com/model-context-protocol-advanced-topics) - Follow-on course on advanced MCP features such as sampling, transports, and production concerns. Free certificate.

### Oracle

- [Become an OCI AI Foundations Associate (learning path)](https://mylearn.oracle.com/ou/learning-path/become-an-oci-ai-foundations-associate/147781) - Free Oracle MyLearn path on AI, ML, and generative AI fundamentals on OCI that prepares for the free associate exam.
- [Become an OCI Generative AI Professional (learning path)](https://mylearn.oracle.com/ou/learning-path/become-an-oci-generative-ai-professional/147863) - Free Oracle path on LLMs, RAG, and the OCI Generative AI service that prepares for the paid professional exam.

## Courses and Learning Paths

### Free Courses with Certificates

Every credential from these platforms is tracked in the tracker linked above.

- [OpenAI Academy](https://academy.openai.com/) - Free courses on applied AI, agents and workflows, and scoping AI solutions, with badges.
- [Microsoft Learn AI training](https://learn.microsoft.com/en-us/training/browse/?terms=ai) - Free modules and learning paths on AI concepts, RAG, agents and responsible AI.
- [Google Skills](https://www.skills.google/) - Free Google Cloud generative AI and responsible AI courses with skill badges.

### GitHub Curricula

- [Generative AI for Beginners](https://github.com/microsoft/generative-ai-for-beginners) - Microsoft's beginner course on building with generative AI.
- [MCP for Beginners](https://github.com/microsoft/mcp-for-beginners) - Microsoft's multi-language curriculum on Model Context Protocol fundamentals.
- [RAG Time](https://github.com/microsoft/rag-time) - Five-week learning journey on RAG concepts and implementation.
- [LLM Course](https://github.com/mlabonne/llm-course) - Roadmaps and Colab notebooks from LLM fundamentals to deployment.
- [Made With ML](https://github.com/GokuMohandas/Made-With-ML) - Course on developing, deploying, and iterating on production ML applications.
- [Agents Towards Production](https://github.com/NirDiamant/agents-towards-production) - Code-first tutorials for taking agents from prototype to production.
- [Anthropic Prompt Engineering Interactive Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial) - Anthropic's hands-on, notebook-based prompt engineering course.
- [Anthropic Courses](https://github.com/anthropics/courses) - Anthropic's courses on the API, prompting and tool use (archived but still useful).
- [Prompt Engineering Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) - Guides and papers on prompt engineering, context engineering, RAG, and agents.
- [LLMs from Scratch](https://github.com/rasbt/LLMs-from-scratch) - Build a GPT-style LLM in PyTorch step by step.

## Architecture Patterns and Guides

- [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) - Anthropic's guide to workflows versus agents and composable patterns.
- [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) - Anthropic on curating context for long-running agents.
- [A practical guide to building agents](https://cdn.openai.com/business-guides-and-resources/a-practical-guide-to-building-agents.pdf) - OpenAI guide to agent design, orchestration and guardrails.
- [Emerging patterns in building GenAI products](https://martinfowler.com/articles/gen-ai-patterns/) - Martin Fowler's site on RAG, guardrails, evals and other production patterns.
- [Patterns for building LLM-based systems](https://eugeneyan.com/writing/llm-patterns/) - Eugene Yan's catalog of evals, RAG, caching, guardrails and feedback patterns.
- [What we learned from a year of building with LLMs](https://applied-llms.org/) - Practitioner lessons on tactics, operations and strategy for LLM products.
- [Emerging architectures for LLM applications](https://a16z.com/emerging-architectures-for-llm-applications/) - Andreessen Horowitz reference stack for LLM apps.
- [12-Factor Agents](https://github.com/humanlayer/12-factor-agents) - Principles for building LLM-powered software that is reliable enough for production customers.

## Cloud Reference Architectures

### AWS

- [AWS Well-Architected Generative AI Lens](https://docs.aws.amazon.com/wellarchitected/latest/generative-ai-lens/generative-ai-lens.html) - Best practices for generative AI workloads across the six pillars.
- [AWS Well-Architected Machine Learning Lens](https://docs.aws.amazon.com/wellarchitected/latest/machine-learning-lens/machine-learning-lens.html) - Best practices for the ML lifecycle on AWS.
- [AWS Generative AI Security Scoping Matrix](https://aws.amazon.com/ai/security/generative-ai-scoping-matrix/) - Framework to classify generative AI use cases and pick security controls.
- [AWS Architecture Center](https://aws.amazon.com/architecture/) - Reference architectures, diagrams and solutions.
- [Amazon Bedrock Samples](https://github.com/aws-samples/amazon-bedrock-samples) - Amazon Bedrock examples spanning agents, knowledge bases, guardrails and model customization.
- [Amazon Bedrock Workshop](https://github.com/aws-samples/amazon-bedrock-workshop) - Hands-on workshop for building with Amazon Bedrock.
- [Generative AI Use Cases on AWS](https://github.com/aws-samples/generative-ai-use-cases) - Deployable AWS reference app bundling many business GenAI use cases, useful for customer demos.
- [Generative AI CDK Constructs](https://github.com/awslabs/generative-ai-cdk-constructs) - AWS CDK constructs that package common generative AI architecture patterns as infrastructure code.
- [AWS MCP Servers](https://github.com/awslabs/mcp) - Official AWS-maintained MCP servers for AWS services and documentation.
- [Generative AI Application Builder on AWS](https://github.com/aws-solutions/generative-ai-application-builder-on-aws) - AWS Solutions reference implementation for rapidly deploying configurable GenAI apps.
- [Amazon SageMaker Examples](https://github.com/aws/amazon-sagemaker-examples) - Notebooks for training, tuning, and deploying models with Amazon SageMaker.
- [AWS Well-Architected Labs](https://github.com/awslabs/aws-well-architected-labs) - Hands-on labs that teach the AWS Well-Architected pillars in practice.

### Microsoft Azure

- [Azure Well-Architected Framework for AI workloads](https://learn.microsoft.com/en-us/azure/well-architected/ai/) - Design principles, areas and checklists for AI on Azure.
- [Azure Architecture Center for AI and ML](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/) - Reference architectures for chat, RAG and agents on Azure.
- [Azure OpenAI gateway guide](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/azure-openai-gateway-guide) - When and how to put a gateway in front of model deployments.
- [Cloud Adoption Framework for AI](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/scenarios/ai/) - Strategy, planning, governance and operations for AI adoption.
- [Azure Search OpenAI Demo](https://github.com/Azure-Samples/azure-search-openai-demo) - Reference RAG app on Azure AI Search and Azure OpenAI.
- [AI Gateway labs](https://github.com/Azure-Samples/AI-Gateway) - Labs for governing models, MCP servers, and agents through Azure API Management as an AI gateway.
- [AI Landing Zones](https://github.com/Azure/AI-Landing-Zones) - Secure, scalable AI landing zone reference architecture with Bicep and Terraform implementations.
- [Agent Landing Zone](https://github.com/Azure/agent-landing-zone) - Enterprise landing zone for AI agent apps on Microsoft Foundry with zero-trust networking and IaC.
- [Microsoft Foundry Baseline](https://github.com/Azure-Samples/microsoft-foundry-baseline) - Reference implementation behind the Microsoft Foundry chat baseline architecture on Microsoft Learn.
- [AI Hub Gateway Solution Accelerator](https://github.com/Azure-Samples/ai-hub-gateway-solution-accelerator) - Accelerator for a central, governed AI API gateway shared across business units.
- [RAG on PostgreSQL](https://github.com/Azure-Samples/rag-postgres-openai-python) - RAG over PostgreSQL rows deployable on Azure, a good structured-data demo.
- [Microsoft Foundry Samples](https://github.com/microsoft-foundry/foundry-samples) - Official samples for building apps and agents on Microsoft Foundry.
- [Azure Architecture Center source](https://github.com/MicrosoftDocs/architecture-center) - Source of the Azure Architecture Center, including AI/ML reference architectures and design guides.

### Google Cloud

- [Google Cloud Well-Architected Framework AI and ML perspective](https://cloud.google.com/architecture/framework/perspectives/ai-ml) - AI and ML guidance across the framework's pillars.
- [Google Cloud Architecture Center for AI and ML](https://cloud.google.com/architecture/ai-ml) - Reference architectures for generative AI, RAG and MLOps.
- [Vertex AI generative AI docs](https://cloud.google.com/vertex-ai/generative-ai/docs/learn/overview) - Official documentation for Gemini and partner models on Vertex AI.
- [Vertex AI Samples](https://github.com/GoogleCloudPlatform/vertex-ai-samples) - Samples for training, deploying, and managing ML and GenAI on Vertex AI.
- [ADK Recipes](https://github.com/google/adk-recipes) - Agent recipes, reference patterns and vertical examples built with Google ADK.

## System Design

- [System Design Primer](https://github.com/donnemartin/system-design-primer) - Free, comprehensive guide to large-scale system design, with interview exercises.
- [System Design 101](https://github.com/ByteByteGoHq/system-design-101) - Visual explanations of system design concepts.
- [System Design course](https://github.com/karanpratapsingh/system-design) - Structured course covering system design building blocks and worked interview problems.
- [Awesome System Design Resources](https://github.com/ashishps1/awesome-system-design-resources) - Free system design concepts and interview resources.
- [Machine Learning Systems Design](https://github.com/chiphuyen/machine-learning-systems-design) - Chip Huyen's booklet on ML systems design with practice exercises.
- [Designing Machine Learning Systems resources](https://github.com/chiphuyen/dmls-book) - Chapter summaries and resources for the book Designing Machine Learning Systems.
- [AI Engineering book resources](https://github.com/chiphuyen/aie-book) - Resources accompanying Chip Huyen's book AI Engineering.
- [Production-Level Deep Learning](https://github.com/alirezadir/Production-Level-Deep-Learning) - Guidelines for taking deep learning systems from prototype to production.
- [ML and LLM system design case studies](https://www.evidentlyai.com/ml-system-design) - Evidently AI's database of 650+ real-world ML and LLM system designs.
- [Machine Learning Systems](https://www.mlsysbook.ai/) - Free open textbook on engineering ML systems.
- [AI Engineering](https://www.oreilly.com/library/view/ai-engineering/9781098166298/) - Chip Huyen's book on building applications with foundation models $.

## Agent Frameworks

- [OpenAI Agents SDK](https://github.com/openai/openai-agents-python) - OpenAI's lightweight framework for multi-agent workflows.
- [Claude Agent SDK for Python](https://github.com/anthropics/claude-agent-sdk-python) - Python SDK for building agents on the Claude Code agent harness.
- [Agent Development Kit (ADK)](https://github.com/google/adk-python) - Google's code-first Agent Development Kit for building and deploying agents.
- [Microsoft Agent Framework](https://github.com/microsoft/agent-framework) - Microsoft's framework for building and orchestrating agents in Python and .NET.
- [LangGraph](https://github.com/langchain-ai/langgraph) - Low-level framework for building stateful, controllable agent graphs.
- [LangChain](https://github.com/langchain-ai/langchain) - Framework for composing LLM apps and agents with tools and retrievers.
- [LlamaIndex](https://github.com/run-llama/llama_index) - Framework for document processing, retrieval, and agents over enterprise data.
- [Pydantic AI](https://github.com/pydantic/pydantic-ai) - Type-safe Python agent framework from the Pydantic team.
- [Strands Agents](https://github.com/strands-agents/harness-sdk) - Model-agnostic open-source agent SDK for Python and TypeScript, originating at AWS.
- [Semantic Kernel](https://github.com/microsoft/semantic-kernel) - Enterprise SDK for C#, Python and Java that plugs LLMs into existing applications.
- [CrewAI](https://github.com/crewAIInc/crewAI) - Framework for orchestrating role-based multi-agent systems.
- [Haystack](https://github.com/deepset-ai/haystack) - Production-oriented pipeline framework for search, RAG and agent applications.
- [Agent Squad](https://github.com/2FastLabs/agent-squad) - Framework for routing conversations across multiple specialized agents.
- [AutoGen](https://github.com/microsoft/autogen) - Multi-agent conversation framework from Microsoft Research, now succeeded by Microsoft Agent Framework.

## Agent Protocols

- [Model Context Protocol docs](https://modelcontextprotocol.io/) - Official documentation, concepts and specification for MCP.
- [MCP specification](https://github.com/modelcontextprotocol/modelcontextprotocol) - The Model Context Protocol specification and official documentation.
- [MCP reference servers](https://github.com/modelcontextprotocol/servers) - Reference MCP servers for common systems.
- [MCP Inspector](https://github.com/modelcontextprotocol/inspector) - Interactive tool for testing and debugging MCP servers.
- [Agent2Agent protocol](https://a2a-protocol.org/) - Official documentation for the A2A protocol.
- [Agent2Agent (A2A) Protocol](https://github.com/a2aproject/A2A) - Agent2Agent open protocol for interoperability between independent agents.
- [Agent Skills](https://github.com/anthropics/skills) - Anthropic's public repository of Agent Skills.

## RAG and Vector Databases

- [RAG Techniques](https://github.com/NirDiamant/RAG_Techniques) - Notebooks demonstrating advanced RAG techniques.
- [GraphRAG](https://github.com/microsoft/graphrag) - Microsoft's knowledge-graph-based RAG system for global, multi-hop questions.
- [pgvector](https://github.com/pgvector/pgvector) - PostgreSQL extension that adds vector similarity search.
- [Qdrant](https://github.com/qdrant/qdrant) - High-performance Rust vector database with filtering and hybrid search.
- [Milvus](https://github.com/milvus-io/milvus) - Cloud-native vector database built for billion-scale search.
- [Weaviate](https://github.com/weaviate/weaviate) - Open-source vector database combining vector and keyword search.
- [Chroma](https://github.com/chroma-core/chroma) - Developer-friendly open-source embedding database, the default for many prototypes.
- [LanceDB](https://github.com/lancedb/lancedb) - Embedded, serverless-friendly multimodal retrieval library.
- [Pinecone Learning Center](https://www.pinecone.io/learn/) - Vendor-written but thorough guides on vector search and RAG.

## AI Gateways and Routing

- [LiteLLM](https://github.com/BerriAI/litellm) - AI gateway that exposes 100+ LLM APIs in one format with cost tracking and guardrails.
- [Portkey AI Gateway](https://github.com/Portkey-AI/gateway) - Fast AI gateway with routing, retries, caching, and built-in guardrails.
- [Agent Router](https://github.com/theagentrouter/agent-router) - Envoy Gateway-based project for unified, policy-controlled access to GenAI services.
- [agentgateway](https://github.com/agentgateway/agentgateway) - Proxy purpose-built for agent-to-tool and agent-to-agent traffic including MCP and A2A.
- [RouteLLM](https://github.com/lm-sys/RouteLLM) - Framework for routing queries between cheap and strong models to cut cost.

## Inference Serving

- [vLLM](https://github.com/vllm-project/vllm) - High-throughput, memory-efficient LLM inference and serving engine.
- [SGLang](https://github.com/sgl-project/sglang) - High-performance serving framework for LLMs and multimodal models.
- [TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM) - NVIDIA library for optimized LLM inference on its GPUs.
- [Triton Inference Server](https://github.com/triton-inference-server/server) - Multi-framework model server for cloud and edge inference.
- [KServe](https://github.com/kserve/kserve) - Kubernetes-native model inference platform for predictive and generative AI.
- [Ray](https://github.com/ray-project/ray) - Distributed compute engine with libraries for training, tuning, and serving.
- [llm-d](https://github.com/llm-d/llm-d) - Kubernetes-native distributed inference stack with disaggregated serving.
- [vLLM Production Stack](https://github.com/vllm-project/production-stack) - Reference Kubernetes deployment for running vLLM at cluster scale.
- [llama.cpp](https://github.com/ggml-org/llama.cpp) - Portable C/C++ LLM inference that runs on CPUs and modest hardware.
- [BentoML](https://github.com/bentoml/BentoML) - Framework for packaging models into inference APIs and multi-model pipelines.
- [SkyPilot](https://github.com/skypilot-org/skypilot) - Runs AI training and serving across clouds and Kubernetes with cost-aware scheduling.
- [Text Generation Inference](https://github.com/huggingface/text-generation-inference) - Hugging Face's LLM serving toolkit, now archived but still a common reference design.
- [MLPerf Inference](https://github.com/mlcommons/inference) - Reference implementations of the MLPerf Inference benchmarks.
- [vLLM documentation](https://docs.vllm.ai/) - Deployment, scaling and tuning guides for vLLM.

## Evaluation

- [promptfoo](https://github.com/promptfoo/promptfoo) - Prompt, agent, and RAG testing with red teaming and vulnerability scanning.
- [DeepEval](https://github.com/confident-ai/deepeval) - Pytest-style evaluation framework for LLM applications.
- [Ragas](https://github.com/vibrantlabsai/ragas) - Metrics and test-data generation for evaluating RAG pipelines (formerly explodinggradients/ragas).
- [OpenAI Evals](https://github.com/openai/evals) - Framework and registry for evaluating LLMs and LLM systems.
- [LM Evaluation Harness](https://github.com/EleutherAI/lm-evaluation-harness) - Standard harness for benchmarking language models on academic tasks.
- [HELM](https://github.com/stanford-crfm/helm) - Stanford's holistic, reproducible evaluation framework for foundation models.
- [Artificial Analysis](https://artificialanalysis.ai/) - Independent benchmarks of model quality, speed and price.
- [LMArena](https://lmarena.ai/) - Crowd-sourced head-to-head model comparisons.

## Observability and LLMOps

- [Langfuse](https://github.com/langfuse/langfuse) - Open-source LLM tracing, evals, and prompt management.
- [Phoenix](https://github.com/Arize-ai/phoenix) - Open-source AI observability and evaluation.
- [OpenLLMetry](https://github.com/traceloop/openllmetry) - OpenTelemetry-based instrumentation for LLM applications.
- [Opik](https://github.com/comet-ml/opik) - Open-source platform for tracing, evaluating and monitoring LLM apps and agents.
- [Helicone](https://github.com/Helicone/helicone) - Open-source LLM observability proxy with one-line integration.
- [MLflow](https://github.com/mlflow/mlflow) - Platform for tracking, evaluating, and deploying ML models and LLM apps.
- [Evidently](https://github.com/evidentlyai/evidently) - Open-source framework for evaluating and monitoring ML and LLM systems.
- [OpenTelemetry generative AI semantic conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) - Standard attributes for tracing LLM calls and agents.
- [Kubeflow](https://github.com/kubeflow/kubeflow) - Cloud-native platform for ML workflows on Kubernetes.
- [Metaflow](https://github.com/Netflix/metaflow) - Human-centric framework for building and deploying ML and AI systems.
- [ZenML](https://github.com/zenml-io/zenml) - Pipeline framework that spans classic ML and agent workflows.
- [Feast](https://github.com/feast-dev/feast) - Open-source feature store for serving ML features consistently.
- [DVC](https://github.com/treeverse/dvc) - Version control for data, models, and ML experiments.

## Cost and FinOps

- [FinOps for AI](https://www.finops.org/wg/finops-for-ai-overview/) - FinOps Foundation guidance on forecasting and managing AI spend.
- [OpenCost](https://github.com/opencost/opencost) - CNCF project for Kubernetes and cloud cost monitoring, useful for GPU workload allocation.
- [genai-prices](https://github.com/pydantic/genai-prices) - Maintained dataset and library for calculating LLM API call prices.
- [tokencost](https://github.com/AgentOps-AI/tokencost) - Client-side token counting and price estimation across hundreds of models.
- [GPTCache](https://github.com/zilliztech/GPTCache) - Semantic cache layer that reduces repeated LLM calls.
- [LLMLingua](https://github.com/microsoft/LLMLingua) - Prompt compression techniques that lower token usage and latency.

## Security and Guardrails

### Frameworks and Standards

- [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) - The most critical security risks for LLM applications and agents.
- [OWASP AI Exchange](https://owaspai.org/) - Open guidance on AI security and privacy threats and controls.
- [MITRE ATLAS](https://atlas.mitre.org/) - Adversary tactics and techniques against AI systems.
- [Google Secure AI Framework](https://saif.google/) - Google's framework and risk map for securing AI systems.
- [Coalition for Secure AI](https://www.coalitionforsecureai.org/) - Industry coalition publishing secure AI frameworks and controls.
- [CSA AI Controls Matrix](https://cloudsecurityalliance.org/artifacts/ai-controls-matrix) - Cloud Security Alliance control framework for AI systems.
- [OWASP Top 10 for LLM Applications project](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications) - Source for the OWASP Top 10 risks for LLM applications.
- [OWASP AI Exchange project](https://github.com/OWASP/www-project-ai-security-and-privacy-guide) - Repository behind the OWASP AI Exchange and AI security and privacy guidance.
- [OWASP AI Testing Guide](https://github.com/OWASP/www-project-ai-testing-guide) - OWASP methodology for security testing of AI systems.
- [MITRE ATLAS data](https://github.com/mitre-atlas/atlas-data) - Machine-readable MITRE ATLAS tactics, techniques, and case studies.
- [CoSAI Secure AI Tooling](https://github.com/cosai-oasis/secure-ai-tooling) - Coalition for Secure AI risk map for identifying and mitigating AI system risks.

### Guardrails and Red Teaming

- [NeMo Guardrails](https://github.com/NVIDIA-NeMo/Guardrails) - Toolkit for adding programmable guardrails to LLM conversational systems.
- [Guardrails AI](https://github.com/guardrails-ai/guardrails) - Input and output validation framework for adding guardrails to LLM apps.
- [Purple Llama](https://github.com/meta-llama/PurpleLlama) - Meta's tools for assessing and improving LLM safety, including Llama Guard and CyberSecEval.
- [garak](https://github.com/NVIDIA/garak) - Vulnerability scanner that probes LLMs for jailbreaks, leakage, and other failures.
- [PyRIT](https://github.com/microsoft/PyRIT) - Microsoft's open-source toolkit for automated red teaming of generative AI systems.
- [Agent Scan](https://github.com/snyk/agent-scan) - Scanner for security issues in AI agents, MCP servers, and agent skills.
- [Presidio](https://github.com/data-privacy-stack/presidio) - PII detection and anonymization framework, often required in enterprise POCs.
- [Adversarial Robustness Toolbox](https://github.com/Trusted-AI/adversarial-robustness-toolbox) - Library for evaluating and defending ML models against adversarial attacks.

### Threat Modeling

- [Threat Composer](https://github.com/awslabs/threat-composer) - Lightweight tool for structured threat modeling.
- [OWASP Threat Dragon](https://github.com/OWASP/threat-dragon) - OWASP's open-source threat modeling diagram tool.
- [Awesome Threat Modelling](https://github.com/hysnsec/awesome-threat-modelling) - Books, courses, and tools for learning and practicing threat modeling.

## Responsible AI and Governance

- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) - Voluntary framework to govern, map, measure and manage AI risk.
- [NIST AI 600-1 Generative AI Profile](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf) - Generative AI risks and suggested actions mapped to the AI RMF.
- [ISO/IEC 42001](https://www.iso.org/standard/81230.html) - Certifiable standard for AI management systems $.
- [EU AI Act](https://eur-lex.europa.eu/eli/reg/2024/1689/oj) - Official text of Regulation (EU) 2024/1689 on artificial intelligence.
- [OECD AI Principles](https://www.oecd.org/en/topics/ai-principles.html) - Intergovernmental principles for trustworthy AI.
- [Responsible AI Toolbox](https://github.com/microsoft/responsible-ai-toolbox) - Dashboards and libraries for model error analysis, fairness, and interpretability.
- [AI Fairness 360](https://github.com/Trusted-AI/AIF360) - Fairness metrics and bias-mitigation algorithms for datasets and models.
- [Fairlearn](https://github.com/fairlearn/fairlearn) - Python package for assessing and improving model fairness.
- [Dioptra](https://github.com/usnistgov/dioptra) - NIST test platform for characterizing trustworthiness of AI models.

## Architecture Documentation

- [C4 model](https://c4model.com/) - Hierarchical approach to diagramming software architecture.
- [arc42](https://arc42.org/) - Template for documenting and communicating software architecture.
- [Architecture Decision Records](https://github.com/architecture-decision-record/architecture-decision-record) - Templates and examples for writing architecture decision records.
- [MADR](https://github.com/adr/madr) - Markdown Architectural Decision Records template and guidance.
- [adr-tools](https://github.com/npryce/adr-tools) - Command-line tools for managing ADRs in a repository.
- [Diagrams](https://github.com/mingrammer/diagrams) - Python diagrams-as-code library for cloud architecture diagrams.
- [Diagram as Code](https://github.com/awslabs/diagram-as-code) - CLI that generates AWS architecture diagrams from YAML.
- [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML) - PlantUML macros for drawing C4 model diagrams.
- [Structurizr](https://github.com/structurizr/structurizr) - Models-as-code tooling for the C4 model.
- [Mermaid](https://github.com/mermaid-js/mermaid) - Markdown-like syntax for flowcharts, sequence, and architecture diagrams.
- [D2](https://github.com/d2lang/d2) - Modern declarative diagram scripting language.
- [Excalidraw](https://github.com/excalidraw/excalidraw) - Hand-drawn style whiteboard for sketching architectures.

## Cookbooks and Example Apps

- [Claude Cookbooks](https://github.com/anthropics/claude-cookbooks) - Notebooks and recipes for common Claude API patterns.
- [Claude Quickstarts](https://github.com/anthropics/claude-quickstarts) - Deployable Claude starter apps such as customer support agents and computer use.
- [OpenAI Cookbook](https://github.com/openai/openai-cookbook) - Examples and guides for the OpenAI API.
- [Gemini Cookbook](https://github.com/google-gemini/cookbook) - Official Gemini API examples and guides.
- [Awesome LLM Apps](https://github.com/Shubhamsaboo/awesome-llm-apps) - Large collection of runnable agent and RAG app examples.
- [AI Engineering Hub](https://github.com/patchy631/ai-engineering-hub) - In-depth tutorials on LLMs, RAG, and real-world agent applications.

## Interview Preparation

- [AI and ML Interviews](https://github.com/alirezadir/AIMLInterviews) - Guide to GenAI, agentic, and ML system design interviews at large tech companies.
- [Machine Learning Interview](https://github.com/khangich/machine-learning-interview) - ML interview study plan with system design case studies from FAANG-style companies.
- [Machine Learning Interviews Book](https://github.com/chiphuyen/ml-interviews-book) - Chip Huyen's book on the ML interview process and practice questions.
- [ML Questions](https://github.com/andrewekhalel/MLQuestions) - Technical interview question bank for ML and computer vision engineers.
- [LLM Interview Questions](https://github.com/llmgenai/LLMInterviewQuestions) - Questions reportedly asked in LLM interviews at AI companies, grouped by topic.
- [LLM Interview Questions and Answers Hub](https://github.com/KalyanKS-NLP/LLM-Interview-Questions-and-Answers-Hub) - 100+ LLM interview questions with answers.
- [Tech Interview Handbook](https://github.com/yangshun/tech-interview-handbook) - Concise coding interview preparation materials.

## Related Awesome Lists

- [Awesome LLM](https://github.com/Hannibal046/Awesome-LLM) - Curated list of LLM papers, frameworks and resources.
- [Awesome Generative AI](https://github.com/steven2358/awesome-generative-ai) - Broad catalog of generative AI products, services, and open-source projects across modalities.
- [Awesome LLMOps](https://github.com/tensorchord/Awesome-LLMOps) - Tool directory for building, serving, and operating LLM applications in production.
- [Awesome MLOps](https://github.com/kelvins/awesome-mlops) - Actively maintained list of MLOps tools grouped by lifecycle stage.
- [Awesome Production Machine Learning](https://github.com/EthicalML/awesome-production-machine-learning) - Large categorized list of open-source libraries for deploying, monitoring, and scaling ML.
- [Awesome AI Agents](https://github.com/e2b-dev/awesome-ai-agents) - Curated list of autonomous AI agents and agent frameworks.
- [Awesome LLM Agents](https://github.com/kaushikb11/awesome-llm-agents) - Focused list of frameworks for building LLM-powered agents.
- [Awesome RAG](https://github.com/Danielskry/Awesome-RAG) - Collection of retrieval-augmented generation techniques, tools, and applications.
- [Awesome MCP Servers](https://github.com/punkpeye/awesome-mcp-servers) - Largest community index of Model Context Protocol servers.
- [Awesome Generative AI Guide](https://github.com/aishwaryanr/awesome-generative-ai-guide) - One-stop GenAI repo with research updates, courses and interview resources.
- [Applied ML](https://github.com/eugeneyan/applied-ml) - Papers and tech blogs on ML in production from real companies.
- [Awesome Scalability](https://github.com/binhnguyennus/awesome-scalability) - Patterns and real-world case studies for scalable, reliable, high-performance systems.
- [Awesome System Design](https://github.com/madd86/awesome-system-design) - Resources on distributed systems and system design fundamentals.
- [Awesome Software Architecture](https://github.com/mehdihadeli/awesome-software-architecture) - Articles, videos, and references on software architecture styles, patterns, and principles.
- [Software Architecture Books](https://github.com/mhadidg/software-architecture-books) - Reading list of books on software and systems architecture.
- [Awesome LLM Security](https://github.com/corca-ai/awesome-llm-security) - Tools, papers, and projects covering LLM attacks and defenses.
- [Awesome AI Security](https://github.com/ottosulin/awesome-ai-security) - Regularly updated list of offensive and defensive AI security resources.
- [Awesome AI Engineering](https://github.com/EldanGS/awesome-ai-engineering) - Sister list for pre-sales AI engineers who run discovery, demos and POCs.
- [Awesome Forward Deployment Engineer](https://github.com/EldanGS/awesome-forward-deployment-engineer) - Sister list for engineers embedded with customers to ship production AI.

## Contributing

Contributions are welcome. Read the [contribution guidelines](contributing.md) first, and follow the [Code of Conduct](code-of-conduct.md).

Found a dead link, an archived repository or a retired exam? [Open an issue](https://github.com/EldanGS/awesome-ai-architect/issues/new/choose).
