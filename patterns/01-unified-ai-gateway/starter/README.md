# Variant: Starter (Minimal)

**Simplest governed AI setup. One provider, basic logging. Ship in a weekend.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/starter/index.html)**

Five scenarios: RAG query, ML inference, agentic workflow, rate limiting, and basic logging/audit.

## When to Use

**Use:** Small team shipping first governed LLM app. One model meets all current needs. Minimal regulatory requirements. Want to get started fast with a clear upgrade path.

**Skip:** Multi-provider routing needed (see any other variant). Complex governance required (see azure-native or multi-platform).

## Stack

| Component | Tool |
|-----------|------|
| Gateway | Simple reverse proxy (nginx/Caddy) |
| Provider | Any single LLM API |
| Search | Simple vector DB (Chroma/pgvector) |
| Guardrails | Basic regex + keyword filter |
| Auth | API keys |
| Monitoring | File-based logs |

Estimated cost: ~$50-200/month (API costs only).

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
