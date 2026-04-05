# Variant: Multi-Platform

**Databricks + Azure AI Foundry + Snowflake with Mosaic AI Gateway**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/multi-platform/index.html)**

Five scenarios: RAG query, ML inference, agentic workflow, sensitive data routing, and Tier 2 bypass. Click any section to explore sub-components.

## When to Use

**Use:** Large enterprise running Databricks, Azure AI, and Snowflake together. Multiple teams consume LLMs independently. Both classic ML and Gen AI coexist. Sensitive data requires provider-level routing.

**Skip:** Single cloud is sufficient (see azure-native or databricks-native). Budget cannot support multi-platform (see open-source).

## Stack

| Component | Platform |
|-----------|----------|
| Data Lake | Databricks (Delta Lake) |
| Vector Search | Databricks Vector Search |
| AI Gateway | Mosaic AI Gateway |
| LLM Providers | DBRX + Azure OpenAI GPT-4o + Snowflake Arctic |
| Guardrails | Azure AI Content Safety |
| Catalog | Unity Catalog |
| Analytics | Snowflake Cortex |

Estimated cost: ~$1,400/month infrastructure.

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/multi-platform/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
