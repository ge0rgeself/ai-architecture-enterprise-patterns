# AI Architecture Enterprise Patterns

**Production-tested architecture patterns for deploying AI/ML systems in regulated enterprises. 110 interactive visualizations across 10 patterns. Play with any of them in your browser.**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Patterns](https://img.shields.io/badge/10_patterns-110_visualizations-purple.svg)](#)
[![Gateway](https://img.shields.io/badge/Gateway-12-blue.svg)](#pattern-01) [![RAG](https://img.shields.io/badge/RAG-10-green.svg)](#pattern-02) [![Agents](https://img.shields.io/badge/Agents-10-orange.svg)](#pattern-03) [![Tools](https://img.shields.io/badge/Tools-8-purple.svg)](#pattern-04) [![LLMOps](https://img.shields.io/badge/LLMOps-10-red.svg)](#pattern-05) [![Gov](https://img.shields.io/badge/Gov-14-teal.svg)](#pattern-06) [![Contam](https://img.shields.io/badge/Contam-12-orange.svg)](#pattern-07) [![Compliance](https://img.shields.io/badge/Compliance-14-blue.svg)](#pattern-08) [![Eval](https://img.shields.io/badge/Eval-10-red.svg)](#pattern-09) [![FinOps](https://img.shields.io/badge/FinOps-10-green.svg)](#pattern-10)

**Industries:** Healthcare (HIPAA), Financial Services (SOX, PCI-DSS), Insurance, Government (FedRAMP), Legal.

### All 110 interactive demos: `https://aman210122.github.io/ai-architecture-enterprise-patterns/`

---

## Pattern 01: Unified AI Gateway (12 variants)
| Cloud | [Azure](patterns/01-unified-ai-gateway/azure-native/) [AWS](patterns/01-unified-ai-gateway/aws-native/) [GCP](patterns/01-unified-ai-gateway/gcp-native/) | Platform | [Databricks](patterns/01-unified-ai-gateway/databricks-native/) [Snowflake](patterns/01-unified-ai-gateway/snowflake-native/) |
|-------|---|---------|---|
| Multi | [Multi-Platform](patterns/01-unified-ai-gateway/multi-platform/) [Multi-Cloud](patterns/01-unified-ai-gateway/multi-cloud/) [Hybrid](patterns/01-unified-ai-gateway/hybrid/) | Self-hosted | [Open Source](patterns/01-unified-ai-gateway/open-source/) [Starter](patterns/01-unified-ai-gateway/starter/) [Federated](patterns/01-unified-ai-gateway/federated/) [Edge](patterns/01-unified-ai-gateway/edge/) |

## Pattern 02: RAG for Regulated Data (10 variants)
| Core | [Standard](patterns/02-rag-regulated-data/standard-rag/) [GraphRAG](patterns/02-rag-regulated-data/graph-rag/) [Agentic](patterns/02-rag-regulated-data/agentic-rag/) [Sensitive](patterns/02-rag-regulated-data/sensitive-data-rag/) |
|------|---|
| Specialized | [Conversational](patterns/02-rag-regulated-data/conversational-rag/) [SQL+Vector](patterns/02-rag-regulated-data/hybrid-sql-vector-rag/) [Multimodal](patterns/02-rag-regulated-data/multimodal-rag/) [Multi-Source](patterns/02-rag-regulated-data/multi-source-rag/) [Real-Time](patterns/02-rag-regulated-data/realtime-rag/) [Evaluation](patterns/02-rag-regulated-data/evaluation-rag/) |

## Pattern 03: Multi-Agent Safety Gates (10 variants)
| Gate | [Linear](patterns/03-multi-agent-safety-gates/linear-chain/) [DAG](patterns/03-multi-agent-safety-gates/dag-orchestration/) [Hierarchical](patterns/03-multi-agent-safety-gates/hierarchical/) [Human](patterns/03-multi-agent-safety-gates/human-in-the-loop/) |
|------|---|
| Decision | [Consensus](patterns/03-multi-agent-safety-gates/consensus/) [Adversarial](patterns/03-multi-agent-safety-gates/adversarial-red-blue/) [Debate](patterns/03-multi-agent-safety-gates/debate/) |
| Advanced | [Reflection](patterns/03-multi-agent-safety-gates/reflection-loop/) [Swarm](patterns/03-multi-agent-safety-gates/swarm/) [Monitor](patterns/03-multi-agent-safety-gates/parallel-monitor/) |

## Pattern 04: Tool Governance (8 variants)
[MCP](patterns/04-agentic-tool-governance/mcp-protocol/) [A2A](patterns/04-agentic-tool-governance/a2a-protocol/) [Function Calling](patterns/04-agentic-tool-governance/function-calling/) [Compound](patterns/04-agentic-tool-governance/compound-tools/) [Sandboxed](patterns/04-agentic-tool-governance/sandboxed-execution/) [Escalation](patterns/04-agentic-tool-governance/tool-escalation/) [Multi-Tenant](patterns/04-agentic-tool-governance/multi-tenant-isolation/) [Discovery](patterns/04-agentic-tool-governance/tool-discovery/)

## Pattern 05: LLMOps Pipeline (10 variants)
| Cloud | [Azure](patterns/05-llmops-pipeline/azure-llmops/) [AWS](patterns/05-llmops-pipeline/aws-llmops/) [GCP](patterns/05-llmops-pipeline/gcp-llmops/) [Databricks](patterns/05-llmops-pipeline/databricks-llmops/) |
|-------|---|
| Self-hosted | [Open Source](patterns/05-llmops-pipeline/open-source-llmops/) [Hybrid](patterns/05-llmops-pipeline/hybrid-llmops/) |
| Specialized | [Prompt](patterns/05-llmops-pipeline/prompt-engineering/) [A/B Test](patterns/05-llmops-pipeline/model-ab-testing/) [Compliance-Gated](patterns/05-llmops-pipeline/compliance-gated/) [Data Pipeline](patterns/05-llmops-pipeline/data-pipeline/) |

## Pattern 06: Governance-as-Architecture (14 variants)
| Measurement | [Embedded](patterns/06-governance-as-architecture/embedded-governance/) [Dashboard](patterns/06-governance-as-architecture/governance-dashboard/) [Decay](patterns/06-governance-as-architecture/decay-detection/) |
|------------|---|
| Automation | [Policy-as-Code](patterns/06-governance-as-architecture/policy-as-code/) [Continuous](patterns/06-governance-as-architecture/continuous-compliance/) |
| Enterprise | [Audit Trail](patterns/06-governance-as-architecture/audit-trail/) [Risk-Tiered](patterns/06-governance-as-architecture/risk-tiered/) [Federation](patterns/06-governance-as-architecture/governance-federation/) |
| Development | [Shift-Left](patterns/06-governance-as-architecture/shift-left-governance/) [Model Cards](patterns/06-governance-as-architecture/model-cards/) |
| Responsible AI | [XAI](patterns/06-governance-as-architecture/xai-explainability/) [Bias](patterns/06-governance-as-architecture/bias-fairness/) [Consent](patterns/06-governance-as-architecture/consent-data-rights/) |
| Meta | [Gov Testing](patterns/06-governance-as-architecture/governance-testing/) |

## Pattern 07: Contamination-Resistant Pipeline (12 variants)
Research-validated from [EMG](https://doi.org/10.5281/zenodo.19411743) and ContamPerc papers.
| Prevention | [Isolation](patterns/07-contamination-resistant-pipeline/isolation-barriers/) [Sanitization](patterns/07-contamination-resistant-pipeline/input-sanitization/) |
|-----------|---|
| Detection | [Validation](patterns/07-contamination-resistant-pipeline/validation-checkpoints/) [Canary](patterns/07-contamination-resistant-pipeline/canary-pipeline/) [Percolation](patterns/07-contamination-resistant-pipeline/contamination-percolation/) [Redundant](patterns/07-contamination-resistant-pipeline/redundant-generation/) |
| Response | [Quarantine](patterns/07-contamination-resistant-pipeline/output-quarantine/) [Degradation](patterns/07-contamination-resistant-pipeline/graceful-degradation/) |
| Recovery | [Rollback](patterns/07-contamination-resistant-pipeline/rollback-capable/) [Lineage](patterns/07-contamination-resistant-pipeline/contamination-lineage/) [Cross-Pipeline](patterns/07-contamination-resistant-pipeline/cross-pipeline/) [Immune](patterns/07-contamination-resistant-pipeline/immune-system/) |

## Pattern 08: Compliance-Aware Data Routing (14 variants)
| Cloud | [Azure](patterns/08-compliance-data-routing/azure-compliance/) [AWS](patterns/08-compliance-data-routing/aws-compliance/) [GCP](patterns/08-compliance-data-routing/gcp-compliance/) |
|-------|---|
| Multi | [Multi-Cloud](patterns/08-compliance-data-routing/multi-cloud-compliance/) [On-Prem](patterns/08-compliance-data-routing/on-prem-compliance/) |
| Routing | [Classification](patterns/08-compliance-data-routing/sensitivity-classification/) [Residency](patterns/08-compliance-data-routing/data-residency-routing/) [Consent](patterns/08-compliance-data-routing/consent-based-routing/) [Dynamic](patterns/08-compliance-data-routing/dynamic-reclassification/) [Cross-Border](patterns/08-compliance-data-routing/cross-border-routing/) |
| Advanced | [Multi-Regulation](patterns/08-compliance-data-routing/multi-regulation/) [Anonymization](patterns/08-compliance-data-routing/anonymization-routing/) [Lineage](patterns/08-compliance-data-routing/data-lineage-routing/) [Temporal](patterns/08-compliance-data-routing/temporal-compliance/) |

## Pattern 09: AI Evaluation & Red Teaming (10 variants)
| Automated | [Red Teaming](patterns/09-evaluation-red-teaming/automated-red-teaming/) [RAGAS](patterns/09-evaluation-red-teaming/ragas-evaluation/) [LLM-as-Judge](patterns/09-evaluation-red-teaming/llm-as-judge/) [Adversarial](patterns/09-evaluation-red-teaming/adversarial-robustness/) |
|-----------|---|
| Human | [Human Eval](patterns/09-evaluation-red-teaming/human-eval/) [Domain-Specific](patterns/09-evaluation-red-teaming/domain-specific-eval/) |
| Continuous | [Safety Bench](patterns/09-evaluation-red-teaming/safety-benchmarking/) [Continuous](patterns/09-evaluation-red-teaming/continuous-eval/) [Bias](patterns/09-evaluation-red-teaming/bias-evaluation/) [Regression](patterns/09-evaluation-red-teaming/regression-testing/) |

## Pattern 10: FinOps for AI (10 variants)
| Cloud | [Azure](patterns/10-finops-for-ai/azure-finops/) [AWS](patterns/10-finops-for-ai/aws-finops/) [GCP](patterns/10-finops-for-ai/gcp-finops/) [Multi-Cloud](patterns/10-finops-for-ai/multi-cloud-finops/) |
|-------|---|
| Optimization | [Token-Level](patterns/10-finops-for-ai/token-level-finops/) [Model Cost](patterns/10-finops-for-ai/model-cost-optimization/) [Cache Economics](patterns/10-finops-for-ai/cache-economics/) |
| Enterprise | [Chargeback](patterns/10-finops-for-ai/chargeback/) [Budget Gov](patterns/10-finops-for-ai/budget-governance/) [Capacity Planning](patterns/10-finops-for-ai/capacity-planning/) |

---

## [GAIF-4](https://github.com/aman210122/gaif-governance-observatory) governance metrics in every pattern | NIST AI RMF, EU AI Act, HIPAA, SOX, PCI-DSS, GDPR, FedRAMP

**Aman Sharma** - Principal Enterprise Architect, AI/ML | 18+ years | [LinkedIn](https://linkedin.com/in/amansharmaarchitect) | [ORCID](https://orcid.org/0009-0005-5107-4485) | [GitHub](https://github.com/aman210122) | License: MIT
