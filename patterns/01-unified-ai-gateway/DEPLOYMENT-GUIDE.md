# Pattern 01: Unified AI Gateway
## Production Deployment Guide

**Version:** 2.0
**Author:** Aman Sharma, Principal Enterprise Architect, AI/ML
**Last Updated:** April 2026

---

## 1. Executive Summary

This document provides the complete production deployment specification for the Unified AI Gateway pattern. The gateway acts as the single control plane through which all LLM and ML traffic flows, enabling policy enforcement, intelligent model routing, cost optimization, and full observability across a multi-provider AI/ML platform.

This pattern has been validated in production serving millions of users across a multi-provider stack spanning Databricks, Azure AI Foundry, and Snowflake. The architecture covers 10 sections across two pipelines (build and runtime) with four cross-cutting governance layers.

---

## 2. Architecture Overview

### 2.1 Two-Pipeline Architecture

The Unified AI Gateway pattern separates concerns into two pipelines:

**Build Pipeline (offline):** How you prepare data, train models, register artifacts, and govern context before any request is served.

```
Data Sources -> Data Prep -> Develop & Evaluate -> Catalog & Registry -> Context Delivery (CSP)
```

**Runtime Pipeline (online):** How requests flow from user to model and back, with governance at every stage.

```
Search & Retrieval -> AI Gateway -> Prompt Processing -> Serving -> Consumption
```

The build pipeline feeds into the runtime pipeline. The Catalog provides models and artifacts to the Gateway. The CSP provides governed context to the Prompt Processing layer. Data Prep feeds embeddings and features to Search and Serving respectively.

### 2.2 Cross-cutting Layers

Four layers span the entire architecture:

- **Governance, Security & Trust:** AI risk classification, bias & fairness, explainability, content policy, guardrails, audit & compliance, agent governance, PHI/PII protection
- **Platform Tenancy:** Enterprise platform management, client data isolation, per-client fine tuning, regulatory compliance, network/compute/storage boundaries
- **Observability & FinOps:** User feedback, usage monitoring, events/metrics/traces, drift detection, cost tracking, token analytics, prompt versioning, model performance
- **Deployment & Infrastructure:** CI/CD, containerization, AI platform services, ML lifecycle, infrastructure as code, secret management, auto-scaling

### 2.3 Request Lifecycle

A complete request moves through the architecture in this sequence:

1. **Consumption layer** receives user request (via copilot, API, agent, or service)
2. **Search & Retrieval** finds relevant context (for RAG workflows; skipped for classic ML)
3. **AI Gateway** authenticates, classifies data sensitivity, applies rate limits, selects provider and model
4. **Prompt Processing** applies input guardrails, assembles context with RAG results, shields against injection
5. **Serving Infrastructure** executes model inference (real-time or batch) and tool calls (MCP/A2A)
6. **Prompt Processing** applies output guardrails, checks for hallucination and data leakage
7. **AI Gateway** logs the complete transaction, attributes cost, caches response if applicable
8. **Consumption layer** returns response to user

The **Catalog** resolves model versions and agent definitions at step 3. The **CSP** enforces context policies and provenance at step 4. **Observability** captures telemetry at every step. **Governance** rules are enforced at steps 3, 4, and 6.

---

## 3. Build Pipeline Specifications

### 3.1 Data Sources

Ingestion layer supporting all data types required for ML features and Gen AI content.

| Data Type | Examples | Platform |
|-----------|----------|----------|
| Structured data | Databases, tables, data warehouses | Databricks Delta Lake, Snowflake |
| Unstructured data | Text, images, audio, video | Databricks, Azure Blob Storage |
| Streaming data | Real-time events, IoT, logs | Databricks Structured Streaming |
| Knowledge graphs | Entity relationships, ontologies | Databricks, Neo4j, custom |
| Enterprise APIs | Internal services, ERP, CRM | API Management layer |
| External data | Third-party feeds, public datasets | Ingestion pipelines |
| Documents/PDFs | Policies, contracts, manuals | Document Intelligence, OCR |

### 3.2 Data Prep (Feature Engineering + Content Processing)

**Feature Engineering (Classic ML):**
Data exploration and profiling, cleansing and enrichment, featurization and normalization, feature store (Databricks Feature Store or Snowflake), auto feature engineering, data versioning and lineage.

**Content Processing (Gen AI):**
Document extraction and OCR (Azure Document Intelligence), chunking strategies (fixed, semantic, recursive), embedding generation (text-embedding-3-large or open models), metadata extraction, summarization, semantic modeling, entity linking, graph construction, multimodal preparation, agentic data prep (AI-assisted pipeline).

**Platform:** Databricks for ML features and embedding pipelines. Snowflake for structured data transformations. Both platforms feed into the Catalog.

### 3.3 Develop & Evaluate Model

**Model Types:**
Foundation LLMs (via provider APIs), ML model training (custom models on Databricks), fine-tuning (full or parameter-efficient), multimodal models, small language models (SLM) for edge deployment.

**Adaptation Methods:**
LoRA and QLoRA for parameter-efficient fine-tuning, DPO (Direct Preference Optimization), RLHF (Reinforcement Learning from Human Feedback), prompt tuning.

**Evaluation:**
LLM-as-judge evaluation, groundedness scoring, red teaming and adversarial testing, benchmark suites, A/B testing, safety scoring, distillation and quantization for deployment optimization.

**Platform:** Databricks MLflow for experiment tracking, model training, and evaluation pipelines.

### 3.4 Catalog & Registry

Central registry for all AI artifacts:

| Artifact Type | Description | Platform |
|--------------|-------------|----------|
| Models | Trained and fine-tuned model versions | Unity Catalog (Databricks) |
| Features | Feature definitions and serving metadata | Databricks Feature Store |
| Functions/Tools | Callable tools for agent workflows | Unity Catalog |
| Prompts | Versioned prompt templates | Unity Catalog / custom |
| Agents | Agent definitions with tool permissions | Unity Catalog |
| Semantic models | Domain ontologies and schemas | Custom registry |
| Indexes | Vector and search index metadata | Databricks Vector Search |
| Context catalog | Governed context products (CSP) | CSP registry |
| Products catalog | Reusable AI product definitions | CSP registry |

### 3.5 Governed Context Delivery (CSP)

The Context Services Platform governs what context reaches models before inference. This is a distinct layer from the AI Gateway and Prompt Processing.

| Capability | Purpose |
|-----------|---------|
| Context Products | Packaged, reusable context bundles for specific use cases |
| Policy Enforcement | Rules governing which context can be used with which models |
| Context Redaction | Automated removal or masking of sensitive data in context |
| Context Provenance | Chain of custody tracking for all context used in inference |
| Context Manifest | Declarative specification of context requirements per use case |
| Context Versioning | Version control for context products and policies |
| Context Quality Scoring | Automated quality assessment of retrieved context |

**Platform:** Built on Databricks with custom components for policy enforcement and provenance tracking.

---

## 4. Runtime Pipeline Specifications

### 4.1 Search & Retrieval

| Method | Description | Use Case |
|--------|-------------|----------|
| Vector search | Embedding similarity search | Standard RAG retrieval |
| GraphRAG | Knowledge graph traversal | Complex entity relationships |
| Keyword/BM25 | Traditional text search | Exact term matching |
| Hybrid retrieval | Combined vector + keyword | Best of both approaches |
| Re-ranking (MMR) | Maximal marginal relevance | Diversity in results |
| Agentic RAG | Agent-driven retrieval with planning | Complex multi-step queries |
| Corrective RAG (CRAG) | Re-retrieval on low confidence | Self-correcting pipelines |
| Self-RAG | Model decides when to retrieve | Selective augmentation |
| Multi-index fusion | Search across multiple indexes | Cross-domain queries |

**Platform:** Databricks Vector Search as the primary retrieval engine.

### 4.2 AI Gateway (Mosaic AI Gateway)

The central control plane. All model traffic routes through this layer.

| Capability | Description | Latency Impact |
|-----------|-------------|---------------|
| LLM routing & fallback | Select provider based on sensitivity, cost, and availability. Fallback chains with circuit breakers. | 1-3ms |
| Semantic caching | Cache responses for semantically similar queries. Reduces cost and latency for repeated patterns. | -50-200ms (savings) |
| Rate limiting & quotas | Per-user, per-team, per-application limits on requests and tokens. Backpressure queuing. | 0-1ms |
| Model interoperability | Unified API across all providers. Applications do not know which provider is serving. | 0ms |
| Load balancing | Distribute traffic across provider endpoints and regions. | 0-1ms |
| Token management | Track, budget, and attribute token consumption. | 0ms |
| API versioning | Version the gateway API independently from provider APIs. | 0ms |

**Key design decision:** The hosting platform is NOT in the serving path. The gateway inspects and routes, but model inference happens at the provider endpoint. BAA/DPA eliminates the need for pre-transmission de-identification.

**Routing Decision Matrix:**

| Sensitivity Level | Description | Allowed Providers | Strategy |
|-------------------|-------------|-------------------|--------------------|
| Level 4 (PHI/PCI) | Regulated sensitive data | DPA/BAA providers only | Compliance-first |
| Level 3 (Confidential) | Business-sensitive with context | DPA providers preferred | Quality-first |
| Level 2 (PII) | Basic personal identifiers | Most providers | Cost-optimized |
| Level 1 (Public) | De-identified or general | All providers | Cost-optimized |

### 4.3 LLM Prompt Processing

**Pre-model (input):**
Input guardrails (Mosaic Gateway function), prompt shields (injection detection), context assembly (combine retrieval + system prompt + user query), prompt augmentation (attach RAG context), LLM orchestration (chain management).

**Post-model (output):**
Output guardrails (sensitive data minimum necessary enforcement), structured output enforcement, hallucination detection and scoring.

**Platform:** Azure AI Content Safety for content classification. Mosaic AI Gateway functions for input/output guardrails.

### 4.4 Serving Infrastructure

| Capability | Description | Platform |
|-----------|-------------|----------|
| Real-time inference | Low-latency model serving endpoints | Databricks Model Serving |
| Batch inference | Scheduled large-scale predictions | Databricks Jobs |
| Function calling | Tool use for LLM-generated actions | Provider-native (OpenAI, Anthropic) |
| MCP Server | Model Context Protocol for tool integration (Anthropic) | Custom / Databricks |
| A2A Server | Agent-to-Agent protocol (Google) | Custom / Databricks |
| API Management | Rate limiting, auth, versioning at the API layer | Azure APIM / Kong |
| Agent code execution | Sandboxed code execution for agent actions | Databricks / custom |
| Edge/on-device | Local inference for latency-critical or offline use | SLM models |

### 4.5 Consumption

| Pattern | Description | Example |
|---------|-------------|---------|
| Human user | Direct interaction via UI | Chat interface, dashboard |
| Copilots & chatbots | Conversational AI embedded in workflows | Customer service bot |
| Embedded AI (APIs) | AI capabilities called by other services | Risk scoring API |
| Service/microservice | AI as a backend service | Document processing pipeline |
| Event-driven | AI triggered by system events | Anomaly detection on data ingest |
| Autonomous agents | Self-directed agents with tool access | Research assistant |
| Personalized UX | AI-tailored user experiences | Recommendation engine |
| Multi-channel | AI delivered across web, mobile, voice | Omnichannel support |

---

## 5. Tier 2: Managed SaaS AI

Certain AI tools operate outside the Unified AI Gateway and are governed separately:

| Category | Tools | Governance |
|----------|-------|-----------|
| Developer copilots | Claude Code, GitHub Copilot, Codex, Gemini Code, DBT Copilot | Acceptable Use Policy + DLP |
| Enterprise copilots | M365 Copilot | Purview DLP required |
| Agent platforms | Foundry Agents (prod), Databricks (dev), Snowflake (analyst) | Platform-native controls |
| Direct LLM sandbox | Direct API access for experimentation | Sandbox policy, no sensitive data |

**Key rule:** No PHI, PCI, or confidential data in Tier 2 tools. Governance is enforced through DLP proxies and acceptable use policies, not through the AI Gateway.

---

## 6. Deployment Topology

### 6.1 High Availability

Minimum two gateway nodes in active-active configuration behind a load balancer. Shared state (rate limit counters, circuit breaker state, policy rules) stored in Redis with AOF persistence and cluster mode.

**Scaling:** 1 node per 500 concurrent requests. Auto-scale trigger at CPU > 70% sustained for 3 minutes. Maximum 8 nodes before evaluating architectural decomposition.

### 6.2 Infrastructure Requirements (Per Gateway Node)

| Resource | Minimum | Recommended |
|----------|---------|-------------|
| CPU | 4 vCPU | 8 vCPU |
| Memory | 8 GB | 16 GB |
| Disk | 50 GB SSD | 100 GB SSD |
| Network | 1 Gbps | 10 Gbps |

### 6.3 Network Security

All connections use TLS 1.3 minimum. Inbound traffic allowed on 443 from application VNet only. Outbound traffic allowed to provider endpoints only (whitelist by FQDN). All other traffic denied.

---

## 7. GAIF-4 Governance Integration

| Metric | Calculation | Threshold (Green) | Threshold (Red) | Measurement Frequency |
|--------|-------------|-------------------|-----------------|----------------------|
| T1PR | Requests passing policy that contained violations / total passed | < 0.05 | > 0.15 | Hourly |
| CFR | Requests with compliance violations / total completed | 0.00 | > 0.01 | Hourly |
| EMR | Dangerous pipeline-level content / total multi-agent completions | 0.00 | > 0.05 | Hourly |
| GDR | Governance effectiveness decay rate per pipeline stage | < 0.03 | > 0.05 | Weekly |

**T1PR measurement:** Run a shadow evaluation on 5% of passed requests using a stricter rule set. Requests the shadow blocks but production passed are Type-1 passes.

**CFR measurement:** Detect on the response processing path. If the model generates content that violates policy (even though input was clean), increment CFR.

**EMR measurement:** Compare individual agent outputs against the final pipeline output. Content that is safe per-agent but dangerous as a composite is an EMR event.

**GDR measurement:** Compare T1PR and CFR across pipeline stages and time windows. Increasing rates indicate governance decay.

---

## 8. Implementation Checklist

### Phase 1: Foundation (Weeks 1-4)
- [ ] Deploy gateway infrastructure (2 nodes, load balancer, Redis)
- [ ] Implement authentication with identity provider
- [ ] Configure RBAC role matrix
- [ ] Set up request/response logging
- [ ] Establish operations dashboard

### Phase 2: Policy Engine (Weeks 5-8)
- [ ] Integrate sensitive data detection (NER + regex)
- [ ] Implement prompt injection detection
- [ ] Configure rate limiting tiers
- [ ] Add content safety guardrails
- [ ] Deploy policy rule versioning
- [ ] Begin T1PR shadow evaluation

### Phase 3: Routing & CSP (Weeks 9-12)
- [ ] Configure sensitivity-based routing matrix
- [ ] Implement cost optimization algorithm
- [ ] Set up fallback chains with circuit breakers
- [ ] Deploy Context Services Platform
- [ ] Integrate Catalog with gateway model resolution
- [ ] Load test at 1,000 concurrent requests

### Phase 4: Observability & Governance (Weeks 13-16)
- [ ] Deploy full audit logging with data redaction
- [ ] Set up governance dashboard with all four GAIF-4 metrics
- [ ] Configure alerting thresholds
- [ ] Implement response processing pipeline
- [ ] Schedule first governance committee review

### Phase 5: Hardening (Weeks 17-20)
- [ ] Complete penetration testing
- [ ] Validate log retention (7 years for healthcare, per requirements)
- [ ] Document disaster recovery runbook
- [ ] Conduct tabletop exercises (provider outage, data breach)
- [ ] Final compliance review with legal
- [ ] Production launch with controlled traffic ramp (10% -> 50% -> 100%)

---

## 9. Cost Model (Monthly Estimate)

| Component | Specification | Cost |
|-----------|--------------|------|
| Gateway nodes (2x) | D4s v5 (4 vCPU, 16 GB) | $280 |
| Load balancer | Standard LB | $25 |
| Redis | Premium P1, cluster mode | $450 |
| Log store | Azure Data Explorer or Delta Lake | $600 |
| Monitoring | Standard tier | $50 |
| **Total infrastructure** | | **~$1,405/month** |

LLM provider costs are pass-through, attributed to consuming teams via the gateway's cost allocation. The gateway adds no markup but provides complete visibility.

---

## 10. Appendix

### A. Glossary

| Term | Definition |
|------|-----------|
| BAA | Business Associate Agreement (HIPAA) |
| CFR | Compliance Failure Rate (GAIF-4) |
| CRAG | Corrective RAG (re-retrieval on low confidence) |
| CSP | Context Services Platform |
| DPA | Data Processing Agreement (GDPR/general) |
| EMR | Emergent Misinformation Rate (GAIF-4) |
| FMAPI | Foundation Model API (Databricks) |
| GAIF-4 | Governance AI Framework v4 |
| GDR | Governance Decay Rate (GAIF-4) |
| MCP | Model Context Protocol (Anthropic) |
| A2A | Agent-to-Agent protocol (Google) |
| MMR | Maximal Marginal Relevance |
| T1PR | Type-1 Pass Rate (GAIF-4) |

### B. References

- GAIF-4 Specification: https://doi.org/10.5281/zenodo.19378438
- GAIF Governance Observatory: https://github.com/aman210122/gaif-governance-observatory
- NIST AI RMF: https://www.nist.gov/artificial-intelligence/risk-management-framework
- Databricks Mosaic AI Gateway Documentation
- Azure API Management Documentation

---

*This document is part of the AI Architecture Enterprise Patterns repository.*

*Governance metrics powered by GAIF Governance Observatory.*

*Designed by Aman Sharma*
