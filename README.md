# AI Architecture Enterprise Patterns

**Production-tested architecture patterns for deploying AI/ML systems in regulated enterprises. Each pattern includes an interactive visualization you can play with in your browser.**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Gateway](https://img.shields.io/badge/AI_Gateway-12-blue.svg)](#pattern-01-unified-ai-gateway)
[![RAG](https://img.shields.io/badge/RAG-10-green.svg)](#pattern-02-rag-for-regulated-data)
[![Agents](https://img.shields.io/badge/Multi--Agent-10-orange.svg)](#pattern-03-multi-agent-pipeline-with-safety-gates)
[![Tools](https://img.shields.io/badge/Tool_Gov-5-purple.svg)](#pattern-04-agentic-ai-with-tool-governance)
[![Interactive](https://img.shields.io/badge/37_visualizations-interactive-purple.svg)](#)

---

## Why This Exists

Most AI architecture guides show you how to build a chatbot. They skip the hard parts: sensitive data routing, compliance gates, governance decay, multi-model orchestration, agent safety boundaries, and the reality that your LLM pipeline has to survive an audit.

This repository collects architecture patterns designed and validated across 18+ years of enterprise architecture in regulated industries.

**Industries:** Healthcare (HIPAA), Financial Services (SOX, PCI-DSS), Insurance, Government (FedRAMP), Legal, and any organization handling sensitive data.

### GitHub Pages

All 37 interactive demos live at `https://aman210122.github.io/ai-architecture-enterprise-patterns/`

---

## Pattern 01: Unified AI Gateway (12 variants)

Route all LLM and ML traffic through a single governance-aware control plane.

| Category | Variants |
|----------|---------|
| Cloud-native | [Azure](patterns/01-unified-ai-gateway/azure-native/), [AWS](patterns/01-unified-ai-gateway/aws-native/), [GCP](patterns/01-unified-ai-gateway/gcp-native/) |
| Platform-native | [Databricks](patterns/01-unified-ai-gateway/databricks-native/), [Snowflake](patterns/01-unified-ai-gateway/snowflake-native/) |
| Multi-platform | [Multi-Platform](patterns/01-unified-ai-gateway/multi-platform/), [Multi-Cloud](patterns/01-unified-ai-gateway/multi-cloud/), [Hybrid](patterns/01-unified-ai-gateway/hybrid/) |
| Self-hosted | [Open Source](patterns/01-unified-ai-gateway/open-source/), [Starter](patterns/01-unified-ai-gateway/starter/), [Federated](patterns/01-unified-ai-gateway/federated/), [Edge](patterns/01-unified-ai-gateway/edge/) |

---

## Pattern 02: RAG for Regulated Data (10 variants)

Retrieval-augmented generation with compliance boundaries at every stage. [Platform mapping](patterns/02-rag-regulated-data/) for Azure, AWS, GCP, Databricks, and open source.

| Category | Variants |
|----------|---------|
| Core RAG | [Standard](patterns/02-rag-regulated-data/standard-rag/), [GraphRAG](patterns/02-rag-regulated-data/graph-rag/), [Agentic](patterns/02-rag-regulated-data/agentic-rag/), [Sensitive Data](patterns/02-rag-regulated-data/sensitive-data-rag/) |
| Specialized | [Conversational](patterns/02-rag-regulated-data/conversational-rag/), [SQL+Vector](patterns/02-rag-regulated-data/hybrid-sql-vector-rag/), [Multimodal](patterns/02-rag-regulated-data/multimodal-rag/), [Multi-Source](patterns/02-rag-regulated-data/multi-source-rag/), [Real-Time](patterns/02-rag-regulated-data/realtime-rag/), [Evaluation](patterns/02-rag-regulated-data/evaluation-rag/) |

---

## Pattern 03: Multi-Agent Pipeline with Safety Gates (10 variants)

Chain specialized LLM agents with safety checkpoints. [Platform mapping](patterns/03-multi-agent-safety-gates/).

| Category | Variants |
|----------|---------|
| Gate-based | [Linear Chain](patterns/03-multi-agent-safety-gates/linear-chain/), [DAG](patterns/03-multi-agent-safety-gates/dag-orchestration/), [Hierarchical](patterns/03-multi-agent-safety-gates/hierarchical/), [Human-in-Loop](patterns/03-multi-agent-safety-gates/human-in-the-loop/) |
| Decision-based | [Consensus](patterns/03-multi-agent-safety-gates/consensus/), [Adversarial](patterns/03-multi-agent-safety-gates/adversarial-red-blue/), [Debate](patterns/03-multi-agent-safety-gates/debate/) |
| Advanced | [Reflection Loop](patterns/03-multi-agent-safety-gates/reflection-loop/), [Swarm](patterns/03-multi-agent-safety-gates/swarm/), [Parallel Monitor](patterns/03-multi-agent-safety-gates/parallel-monitor/) |

---

## Pattern 04: Agentic AI with Tool Governance (5 variants)

Governance on what agents can DO, not just what they say. [Platform mapping](patterns/04-agentic-tool-governance/).

| Variant | Protocol | Demo |
|---------|---------|------|
| [MCP Protocol](patterns/04-agentic-tool-governance/mcp-protocol/) | Model Context Protocol (Anthropic) - typed tool schemas | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/04-agentic-tool-governance/mcp-protocol/index.html) |
| [A2A Protocol](patterns/04-agentic-tool-governance/a2a-protocol/) | Agent-to-Agent (Google) - peer-to-peer collaboration | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/04-agentic-tool-governance/a2a-protocol/index.html) |
| [Function Calling](patterns/04-agentic-tool-governance/function-calling/) | Provider-native (OpenAI, Bedrock, Gemini) | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/04-agentic-tool-governance/function-calling/index.html) |
| [Compound Tools](patterns/04-agentic-tool-governance/compound-tools/) | Tools chaining other tools with inter-tool governance | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/04-agentic-tool-governance/compound-tools/index.html) |
| [Sandboxed Execution](patterns/04-agentic-tool-governance/sandboxed-execution/) | Agent-generated code in isolated containers | [Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/04-agentic-tool-governance/sandboxed-execution/index.html) |

---

### Future Patterns

| # | Pattern | Variants | Status |
|---|---------|----------|--------|
| 05 | LLMOps Pipeline | Azure, AWS, GCP, Databricks, OSS, Hybrid | Planned |
| 06 | Governance-as-Architecture | Embedded, Dashboard, Policy-as-Code, Decay | Planned |
| 07 | Contamination-Resistant Pipeline | Isolation, Validation, Canary, Rollback | Planned |
| 08 | Compliance-Aware Data Routing | Azure, AWS, GCP, Multi-Cloud, On-Prem | Planned |
| 09 | AI Evaluation & Red Teaming | Automated, RAGAS, LLM-as-Judge, Human, Safety | Planned |
| 10 | FinOps for AI | Azure, AWS, GCP, Multi-Cloud, Token-Level | Planned |

---

## Governance Integration

Every pattern includes quantitative metrics from [GAIF-4](https://github.com/aman210122/gaif-governance-observatory): T1PR, CFR, EMR, GDR.

## Standards: NIST AI RMF, EU AI Act, WHO AI Ethics, HIPAA, SOX, PCI-DSS, GDPR, FedRAMP

---

## Author

**Aman Sharma** - Principal Enterprise Architect, AI/ML | 18+ years in regulated industries

[LinkedIn](https://linkedin.com/in/amansharmaarchitect) | [ORCID](https://orcid.org/0009-0005-5107-4485) | [GitHub](https://github.com/aman210122)

**Related:** [GAIF Governance Observatory](https://github.com/aman210122/gaif-governance-observatory)

---

## License

MIT License. See [LICENSE](LICENSE) for details.
