# Variant: Federated Gateway

**Multiple gateway instances per business unit. Central governance plane.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/federated/index.html)**

Five scenarios: RAG query (BU-local), ML inference, agentic workflow, cross-BU request routing, and enterprise policy sync (central plane pushes to all BU gateways).

## When to Use

**Use:** 10+ teams running AI independently. Each BU needs autonomy to pick models and providers. Enterprise audit requires unified view. Central governance without blocking innovation. Per-BU cost attribution.

**Skip:** Single team (see any single-gateway variant). Centralized control is acceptable (see azure-native or multi-platform).

## Architecture

| Layer | Purpose |
|-------|---------|
| Central governance plane | Enterprise policies, audit aggregation, cost dashboard, compliance rules |
| BU gateway instances | Local routing, BU-specific models, BU-owned data, local policies |
| Policy sync | Central pushes enterprise rules to all BU gateways (30s propagation) |
| BU autonomy | Each BU picks their own models, providers, and local policies |

Estimated cost: ~$2,000+/month (scales with BU count).

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
