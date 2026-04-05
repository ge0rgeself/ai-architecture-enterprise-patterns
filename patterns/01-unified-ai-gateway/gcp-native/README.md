# Variant: GCP Native

**Full Google Cloud ecosystem. Apigee + Vertex AI + Gemini + Model Armor.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/gcp-native/index.html)**

Five scenarios: RAG query (Vertex AI Search), ML inference (Vertex AI endpoints), agentic workflow (Agent Builder), sensitive data (VPC Service Controls), and Google Search grounding with citations.

## When to Use

**Use:** Google Cloud shop. Need Gemini multimodal reasoning. Vertex AI Search for retrieval. Model Armor for safety. Google Search grounding for factual accuracy with citations.

**Skip:** Need Azure features (see azure-native). Need AWS features (see aws-native).

## Stack

| Component | GCP Service |
|-----------|------------|
| Gateway | Apigee (GenAI proxy policies) |
| LLM | Vertex AI (Gemini 2.0, Gemini 1.5 Pro) |
| Search | Vertex AI Search |
| Guardrails | Model Armor |
| Auth | Cloud IAM + IAP |
| DLP | Cloud DLP API |
| Monitoring | Cloud Monitoring + Trace |
| IaC | Terraform |

Estimated cost: ~$850/month infrastructure.

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/gcp-native/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
