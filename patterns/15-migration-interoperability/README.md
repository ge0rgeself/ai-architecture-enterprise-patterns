# Pattern 15: Migration and Interoperability
**Assess, abstract, migrate, validate AI systems across clouds and providers. 12 variants. Zero downtime migration with quality preservation and GAIF-4 governance continuity.**

Enterprises do not start from zero. They have existing AI systems, vendor lock-in, multiple frameworks, models scattered across clouds. This pattern addresses how to migrate, standardize, and interoperate without rebuilding everything.

| Migration Area | Variant |
|---------------|---------|
| Re-platform across clouds | [Cloud Migration](cloud-migration/) |
| GPT to Claude to Gemini | [Model Portability](model-portability/) |
| OpenAI/Anthropic/Bedrock | [API Compatibility](api-compatibility/) |
| LangChain + SK + CrewAI | [Multi-Framework](multi-framework/) |
| Move vector stores | [Vector Index Migration](vector-index-migration/) |
| Cross-model prompts | [Prompt Portability](prompt-portability/) |
| Embeddings, metadata | [Data Migration](data-migration/) |
| Score proprietary deps | [Vendor Lock-in Assessment](vendor-lock-in-assessment/) |
| Parallel old + new | [Dual-Run Strategy](dual-run-strategy/) |
| LiteLLM unified API | [Model Abstraction Layer](model-abstraction-layer/) |
| GAIF-4 across clouds | [Cross-Platform Governance](cross-platform-governance/) |
| Retire old systems | [Sunset Planning](sunset-planning/) |

## Migration Quality Checklist
| Check | Requirement |
|-------|------------|
| Quality | Post-migration eval score >= pre-migration (same golden dataset) |
| Latency | P95 latency within 10% of pre-migration baseline |
| Cost | Migration cost tracked separately, post-migration cost <= budget |
| Governance | GAIF-4 metrics continuous through migration (no gap) |
| Rollback | Every step reversible, rollback tested before go-live |
| Data | Zero data loss, checksum verified, row counts matched |

*[GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
