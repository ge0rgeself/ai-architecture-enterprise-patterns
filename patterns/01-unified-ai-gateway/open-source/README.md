# Variant: Open Source

**LiteLLM + vLLM/Ollama + Llama/Mistral. Fully self-hosted, zero cloud dependencies.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/open-source/index.html)**

Five scenarios: RAG query, ML inference, agentic workflow, sensitive data (all on-prem), and air-gapped deployment.

## When to Use

**Use:** Data sovereignty. Air-gapped environments. Budget-constrained. Full source code ownership. Government/defense. Fine-tuning without vendor exposure.

**Skip:** GPT-4o reasoning required (see azure-native). Enterprise support needed (see databricks-native).

## Stack

| Component | Tool |
|-----------|------|
| Gateway | LiteLLM proxy |
| Serving | vLLM / Ollama |
| Models | Llama 3.1, Mistral, Phi-3 |
| Vector DB | ChromaDB / Qdrant |
| Guardrails | NeMo Guardrails |
| Auth | Keycloak |
| Monitoring | Prometheus + Grafana |
| Orchestration | LangChain / LangGraph |

Estimated cost: ~$400/month (compute only).

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/open-source/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
