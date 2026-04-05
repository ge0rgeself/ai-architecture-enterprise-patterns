# Pattern 02: RAG for Regulated Data

**Retrieval-augmented generation with compliance boundaries at every pipeline stage.**

## Which Variant Should You Use?

| Your situation | Variant |
|---------------|---------|
| Standard document Q&A | [Standard RAG](standard-rag/) |
| Complex entity relationships | [GraphRAG](graph-rag/) |
| Queries need self-correcting retrieval | [Agentic RAG](agentic-rag/) |
| Data across multiple platforms | [Multi-Source RAG](multi-source-rag/) |
| PHI/PII in documents, strict compliance | [Sensitive Data RAG](sensitive-data-rag/) |

## Architecture (11 sections, 2 pipelines)

**Ingestion Pipeline:** Document Sources -> Extraction -> Chunking & Embedding -> Vector Store -> Metadata Catalog

**Query Pipeline:** Query Processing -> Retrieval -> Context Assembly -> Generation -> Validation -> Response

**Cross-cutting:** Data Classification & Compliance, Retrieval Quality & Observability

## RAG Quality Metrics

| Metric | What It Measures |
|--------|-----------------|
| Retrieval precision | Relevant chunks / total retrieved |
| Groundedness | Answer supported by retrieved context |
| Hallucination rate | Claims not in source documents |
| Citation accuracy | Citations match source content |

*Governance: [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
