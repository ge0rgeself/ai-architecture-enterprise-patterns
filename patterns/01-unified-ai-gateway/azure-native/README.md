# Variant: Azure Native

**Full Microsoft ecosystem. Azure APIM + Azure OpenAI + Content Safety + Entra ID.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/azure-native/index.html)**

Five scenarios: RAG query, ML inference, agentic workflow (Prompt Flow), sensitive data (BAA + private endpoints), and M365 Copilot extension.

## When to Use

**Use:** Microsoft shop with Entra ID. Need GPT-4o/4.1 reasoning. BAA for healthcare. M365 Copilot extensibility. Purview DLP.

**Skip:** Need open-weight model control (see databricks-native). Multi-cloud strategy (see multi-cloud).

## Stack

| Component | Azure Service |
|-----------|--------------|
| Gateway | Azure API Management (GenAI policies) |
| LLM | Azure OpenAI (GPT-4o, GPT-4.1, GPT-4o-mini) |
| Search | Azure AI Search (vector + semantic ranking) |
| Guardrails | Azure AI Content Safety + Prompt Shields |
| Auth | Entra ID (Managed Identity) |
| DLP | Microsoft Purview |
| Monitoring | Azure Monitor + App Insights |

Estimated cost: ~$900/month infrastructure.

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/azure-native/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
