# Variant: Multi-Cloud

**Azure OpenAI + AWS Bedrock + GCP Vertex AI. Kong gateway for vendor neutrality.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/multi-cloud/index.html)**

Five scenarios: RAG query, ML inference, agentic workflow, sensitive data (region-specific routing), and cost arbitrage.

## When to Use

**Use:** Multi-cloud strategy. Vendor lock-in avoidance. Best-of-breed model selection. Data residency requiring region-specific routing.

**Skip:** Single cloud is sufficient (see azure-native or databricks-native). Budget is tight (see open-source).

## Stack

| Component | Service |
|-----------|---------|
| Gateway | Kong (vendor-neutral) |
| Providers | Azure OpenAI + AWS Bedrock + GCP Vertex AI |
| IaC | Terraform (multi-cloud) |
| Monitoring | Datadog / Grafana + OpenTelemetry |
| Secrets | HashiCorp Vault |

Estimated cost: ~$1,200/month infrastructure.

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/multi-cloud/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
