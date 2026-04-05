# Variant: Sensitive Data RAG

**PHI/PII-aware retrieval with classification at every stage. Zero-trust access control.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/02-rag-regulated-data/sensitive-data-rag/index.html)**

Scenarios: PHI query, ACL-gated retrieval, minimum necessary, BAA routing, PHI-redacted audit.

## When to Use

**Use:** Documents contain PHI/PII. HIPAA/PCI/GDPR compliance. Chunk-level access control. PHI-redacted audit logs.

**Skip:** Data is not sensitive (see standard-rag). No regulatory requirements (see standard-rag).

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/02-rag-regulated-data/sensitive-data-rag/index.html)) |
| [../README.md](../README.md) | Decision guide for all RAG variants |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
