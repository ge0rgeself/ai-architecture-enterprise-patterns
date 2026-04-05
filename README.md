# AI Architecture Enterprise Patterns

**Production-tested architecture patterns for deploying AI/ML systems in regulated enterprises. Each pattern includes an interactive visualization you can play with in your browser.**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Patterns](https://img.shields.io/badge/patterns-12-blue.svg)](#pattern-catalog)
[![Interactive](https://img.shields.io/badge/visualizations-interactive-purple.svg)](#how-it-works)

---

## Why This Exists

Most AI architecture guides show you how to build a chatbot. They skip the hard parts: sensitive data routing, compliance gates, governance decay, multi-model orchestration, agent safety boundaries, and the reality that your LLM pipeline has to survive an audit.

This repository collects architecture patterns designed and validated across 18+ years of enterprise architecture in regulated industries. Each pattern includes an interactive browser-based visualization with animated data flow, a production deployment guide, and governance metrics mapping.

**Industries:** Healthcare (HIPAA), Financial Services (SOX, PCI-DSS), Insurance, Government (FedRAMP), Legal, and any organization handling sensitive data under regulatory constraints.

---

## How It Works

**Interactive visualization** - Open the HTML file in any browser. Click scenario buttons to watch data flow through the architecture end-to-end. Click any section to expand and explore sub-components. No install, no dependencies.

**Production deployment guide** - Comprehensive documentation covering component specs, deployment topology, security controls, regulatory mapping, implementation checklist, and cost model.

### GitHub Pages Setup

Interactive demos are hosted via GitHub Pages at `https://aman210122.github.io/ai-architecture-enterprise-patterns/`

---

## Pattern Catalog

### Pattern 01: Unified AI Gateway

Route all LLM and ML traffic through a single governance-aware control plane for policy enforcement, intelligent routing, and full observability.

**Cloud-native variants:**

| Variant | Stack | Demo |
|---------|-------|------|
| [Azure Native](patterns/01-unified-ai-gateway/azure-native/) | Azure APIM + Azure OpenAI + Content Safety + Entra ID | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/azure-native/index.html) |
| AWS Native | API Gateway + Bedrock + Guardrails for AI + IAM | Coming soon |
| GCP Native | Apigee + Vertex AI + Gemini + Model Armor | Coming soon |

**Platform-native variants:**

| Variant | Stack | Demo |
|---------|-------|------|
| [Databricks Native](patterns/01-unified-ai-gateway/databricks-native/) | Mosaic AI GW + FMAPI + Unity Catalog | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/databricks-native/index.html) |
| Snowflake Native | Cortex + Snowpark + Arctic + Streamlit | Coming soon |

**Multi-platform variants:**

| Variant | Stack | Demo |
|---------|-------|------|
| [Multi-Platform](patterns/01-unified-ai-gateway/multi-platform/) | Databricks + Azure AI Foundry + Snowflake | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/multi-platform/index.html) |
| [Multi-Cloud](patterns/01-unified-ai-gateway/multi-cloud/) | Kong + Azure OpenAI + AWS Bedrock + GCP Vertex AI | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/multi-cloud/index.html) |

**Self-hosted:**

| Variant | Stack | Demo |
|---------|-------|------|
| [Open Source](patterns/01-unified-ai-gateway/open-source/) | LiteLLM + vLLM/Ollama + Llama/Mistral | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/open-source/index.html) |

### Future Patterns

| # | Pattern | Status |
|---|---------|--------|
| 02 | RAG for Regulated Data | Planned |
| 03 | Multi-Agent Pipeline with Safety Gates | Planned |
| 04 | Governance-as-Architecture | Planned |
| 05 | Contamination-Resistant Pipeline | Planned |
| 06 | Risk-Tiered AI Deployment | Planned |

---

## Architecture Coverage

Every pattern maps to a complete enterprise AI/ML reference architecture with 10 sections across two pipelines:

**Build Pipeline:** Data Sources, Data Prep, Develop & Evaluate, Catalog & Registry, Governed Context Delivery (CSP)

**Runtime Pipeline:** Search & Retrieval, AI Gateway, Prompt Processing, Serving Infrastructure, Consumption

**Cross-cutting:** Governance Security & Trust, Platform Tenancy, Observability & FinOps, Deployment & Infrastructure

---

## Governance Integration

Every pattern includes quantitative metrics from [GAIF-4](https://github.com/aman210122/gaif-governance-observatory):

| Metric | What It Measures |
|--------|-----------------|
| **T1PR** | Contaminated outputs bypassing safety filters |
| **CFR** | Policy violations in completed requests |
| **EMR** | Dangerous content emerging at the pipeline level |
| **GDR** | Governance effectiveness degrading over time |

---

## Standards Mapping

NIST AI RMF, EU AI Act, WHO AI Ethics, HIPAA, SOX, PCI-DSS, GDPR, FedRAMP

---

## Author

**Aman Sharma** - Principal Enterprise Architect, AI/ML | 18+ years in regulated industries

[LinkedIn](https://linkedin.com/in/amansharmaarchitect) | [ORCID](https://orcid.org/0009-0005-5107-4485) | [GitHub](https://github.com/aman210122)

**Related:** [GAIF Governance Observatory](https://github.com/aman210122/gaif-governance-observatory) | [Research Papers](https://orcid.org/0009-0005-5107-4485)

---

## License

MIT License. See [LICENSE](LICENSE) for details.
