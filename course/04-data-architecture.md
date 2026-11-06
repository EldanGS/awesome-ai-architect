# Domain 4: Data Architecture for AI

**Weight: 12%** · **Time: 8-10 hours** · [Back to course](README.md)

Model quality is capped by data quality. This domain covers how enterprise data is ingested, prepared, indexed, permissioned and kept fresh for RAG and agents.

## Learning objectives

- [ ] Design an ingestion pipeline: connectors, parsing, chunking, enrichment, embedding, indexing.
- [ ] Choose a chunking strategy for a document type and justify it.
- [ ] Compare vector databases and search engines and pick one for a scenario.
- [ ] Explain hybrid search, re-ranking and metadata filtering.
- [ ] Decide when a knowledge graph (GraphRAG) or SQL tool beats vector search.
- [ ] Design permission-aware retrieval, freshness and deletion (right to be forgotten).

## Core concepts

### Ingestion pipeline

```text
Sources -> Connectors -> Parse (PDF, HTML, Office, images via OCR)
        -> Clean and de-duplicate -> Chunk -> Enrich (title, section, date, owner, ACL)
        -> Embed -> Index (vector + keyword) -> Monitor freshness and drift
```

Treat ingestion as a **data pipeline** with orchestration, retries, lineage and tests, not a one-off notebook.

### Chunking strategies

| Strategy | Works for | Trade-off |
| --- | --- | --- |
| Fixed size with overlap | Uniform prose. | Simple; can split mid-thought. |
| Structure-aware (headings, sections, tables) | Manuals, policies, wikis. | Needs good parsing; best default for enterprise docs. |
| Semantic chunking | Long narrative text. | Extra compute at ingestion. |
| Parent-child (small chunks retrieved, larger parent returned) | Precise retrieval with enough context. | More storage and logic. |
| Contextual chunking (prepend a short summary of the document to each chunk) | Chunks that are ambiguous alone. | Extra LLM calls at ingestion; often a big recall gain. |

Tables, code and forms usually need special handling: keep tables whole, convert to markdown, or store structured data in a database and query it with a tool.

### Retrieval quality stack

1. **Metadata filters** first (tenant, permissions, product, date).
2. **Hybrid search**: dense vectors for meaning plus keyword (BM25) for exact terms like part numbers.
3. **Re-ranking** with a cross-encoder or re-rank API on the top 20-50 candidates.
4. **Query rewriting** for conversational follow-ups ("what about the second one?").
5. Return a small number of high-quality chunks with citations.

### Choosing a store

| Option | Good fit | Consider |
| --- | --- | --- |
| Vector extension in your existing database (pgvector, MongoDB Atlas Vector Search, and similar) | Moderate scale, want one system, transactional joins. | Tuning at large scale. |
| Dedicated vector database (Qdrant, Weaviate, Milvus, Pinecone, Chroma) | Large scale, high QPS, advanced filtering. | Another system to run and secure. |
| Search engine with vectors (Elasticsearch, OpenSearch, Azure AI Search, Vertex AI Search) | Hybrid search and existing search teams. | Licensing and cost. |
| Graph database (Neo4j and others) | Relationship-heavy questions across entities. | Modeling effort; graph construction cost. |
| Warehouse or lakehouse with SQL tool | Numeric and aggregate questions. | Text-to-SQL accuracy and permissions. |

### When vectors are the wrong tool

- "What was total revenue by region last quarter?" needs a **SQL tool** over governed data, not similar text.
- "Which suppliers are linked to sanctioned entities through subsidiaries?" needs a **graph**.
- "What does clause 7.2 of contract 4411 say?" needs **exact lookup** by ID.

Good architectures route between retrieval methods.

### Governance

| Concern | Control |
| --- | --- |
| Access | Propagate source ACLs into chunk metadata; filter at query time with the user's identity. |
| Freshness | Incremental sync with change data capture or webhooks; show document dates in answers. |
| Deletion | Track chunk lineage to source documents; delete embeddings when sources are deleted. |
| Sensitive data | Classify and redact PII before indexing if it is not needed for the use case. |
| Quality | Track retrieval metrics (recall at k, context precision) on an evaluation set. |

## Patterns and anti-patterns

**Patterns**

- Store raw, parsed and chunked versions so you can re-chunk without re-crawling.
- Version the index alongside the embedding model and chunking configuration.
- Measure retrieval separately from generation.

**Anti-patterns**

- Indexing everything "just in case", including stale and duplicate content.
- Copying documents into a vector store and losing their permissions.
- Debugging bad answers only by changing the prompt when retrieval is the cause.

## Reading list

- [RAG Techniques](https://github.com/NirDiamant/RAG_Techniques) - Tutorials for chunking, hybrid search, re-ranking and advanced RAG.
- [RAGFlow](https://github.com/infiniflow/ragflow) - Open-source RAG engine with deep document understanding.
- [Microsoft GraphRAG](https://github.com/microsoft/graphrag) - Graph-based retrieval over private datasets.
- [pgvector](https://github.com/pgvector/pgvector) - Vector similarity search inside PostgreSQL.
- [Qdrant](https://github.com/qdrant/qdrant) - Open-source vector database with rich filtering.
- [Unstructured](https://github.com/Unstructured-IO/unstructured) - Parsing and pre-processing for PDFs, HTML, Office and images.
- [Docling](https://github.com/docling-project/docling) - Document conversion with layout and table understanding.
- [Introducing Contextual Retrieval](https://www.anthropic.com/news/contextual-retrieval) - Anthropic's write-up on contextual embeddings and BM25 for better recall.
- [Awesome Data Engineering](https://github.com/igorbarinov/awesome-data-engineering) - Pipelines, orchestration and storage tools.

## Free credentials for this domain

From the [tracker](../free-certifications/README.md#rag-data-and-vector-search):

- Microsoft Learn: *Introduction to retrieval-augmented generation concepts*.
- Salesforce Trailhead: *Data Fundamentals for AI* and *Grounding an Agent with Data*.
- Kaggle Learn: *Intro to SQL* and *Data Cleaning*.
- Google Skills: *Vector Search and Embeddings*.
- AWS Skill Builder: *AWS Databases for Agentic AI Demonstrated* microcredential.

## Hands-on lab: retrieval bake-off

1. Collect 30-50 public documents of mixed types (PDF manuals, HTML pages, a spreadsheet).
2. Write 40 questions with the source passage that answers each.
3. Index the corpus three ways: fixed-size chunks, structure-aware chunks, structure-aware plus contextual summaries.
4. Measure recall at 5 for each with dense only, then with hybrid search plus a re-ranker.
5. Add an ACL field to chunks and prove that a test user cannot retrieve a restricted document.
6. **Deliverable:** results table and a recommendation for production configuration.

## Review questions

1. Users search for exact product codes like "XK-4410-B" and vector search misses them. What fixes this?

   <details><summary>Answer</summary>

   Hybrid search: add keyword (BM25) retrieval and fuse the results with vector search, optionally followed by re-ranking.

   </details>

2. A finance user asks "What was Q3 gross margin by product line?" The RAG system returns paragraphs from the annual report. What is the better design?

   <details><summary>Answer</summary>

   Route numeric and aggregate questions to a governed SQL tool over the warehouse, with the user's permissions, and have the model explain the result.

   </details>

3. A document is deleted in SharePoint, but the assistant still quotes it. What was missing?

   <details><summary>Answer</summary>

   Lineage from chunks to source documents plus incremental sync that deletes embeddings when sources are deleted.

   </details>

4. Why store parsed documents separately from embeddings?

   <details><summary>Answer</summary>

   So you can re-chunk or re-embed (for a new model or strategy) without re-crawling and re-parsing every source.

   </details>

5. You moved to a pgvector table and quality dropped at 50 million chunks with heavy filters. What options do you evaluate?

   <details><summary>Answer</summary>

   Index tuning (HNSW parameters, partial indexes, partitioning by tenant), pre-filtering strategy, or moving to a dedicated vector store or search engine built for filtered vector search at scale.

   </details>

6. Name two metrics that measure retrieval quality independent of the LLM.

   <details><summary>Answer</summary>

   Recall at k (or hit rate) and context precision; mean reciprocal rank (MRR) and nDCG are also common.

   </details>
