# Variant: Databricks Native

**Everything on Databricks. Zero external provider dependencies.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/databricks-native/index.html)**

Five scenarios: RAG query, ML inference, agentic workflow, model swap (A/B testing open-weight models), and sensitive data routing.

## When to Use

**Use:** Standardized on Databricks. Prefer open-weight models (DBRX, Llama, Mixtral). Data sovereignty (nothing leaves VPC). Fine-tune on proprietary data.

**Skip:** Need GPT-4o reasoning (see azure-native or multi-platform). Multiple data platforms required (see multi-platform).

## Stack

| Component | Databricks Service |
|-----------|-------------------|
| Gateway | Mosaic AI Gateway |
| Models | DBRX, Llama 3.1, Mixtral 8x7B |
| Serving | Foundation Model API (FMAPI) |
| Search | Databricks Vector Search |
| Catalog | Unity Catalog |
| Guardrails | Mosaic AI Gateway functions |
| Monitoring | Lakehouse Monitoring + Inference Tables |

Estimated cost: ~$800/month infrastructure.

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/databricks-native/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
