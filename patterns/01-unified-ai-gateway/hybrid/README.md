# Variant: Hybrid (Cloud + On-Premises)

**Dual-tier architecture. Cloud for general queries, on-prem for sensitive data.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/hybrid/index.html)**

Five scenarios: RAG query (cloud path), ML inference, agentic workflow, sensitive data (on-prem path where data never leaves your network), and cloud failover (on-prem down, cloud handles general traffic).

## When to Use

**Use:** Some data classes cannot go to any cloud provider. Need cloud performance for general workloads but regulatory requirements for sensitive data. Government, defense, healthcare with strict data residency. Want gradual cloud migration with on-prem fallback.

**Skip:** All data can go to cloud with BAA/DPA (see azure-native or aws-native). Full self-hosting preferred (see open-source).

## Architecture

This variant is architecturally different from all others. It runs two gateway instances:

| Tier | Gateway | Models | Data allowed |
|------|---------|--------|-------------|
| Cloud | Cloud provider APIM | GPT-4o, Claude 3.5 | General, de-identified, public |
| On-prem | Self-hosted proxy | Llama 3.1, Mistral | All data including PHI, PCI, classified |

A classification engine at the ingress point scans every request, determines data sensitivity, and routes to the appropriate tier. Sensitive data never touches the cloud tier.

Estimated cost: ~$1,600/month (cloud + on-prem compute).

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/hybrid/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
