# Deployment Guide: Migration and Interoperability
## Prerequisites: Target platform provisioned, eval suite (P09) ready, governance (P06) configured
## Steps
1. Inventory all existing AI systems: models, endpoints, prompts, data, costs, owners
2. Score migration readiness per system: complexity, risk, dependencies, business impact
3. Map vendor lock-in: proprietary APIs, SDKs, data formats, model formats per system
4. Identify technical debt: ungoverned prompts, unversioned models, missing tests
5. Deploy model abstraction layer (LiteLLM): unified API across providers
6. Build prompt portability layer: cross-model adaptation with testing
7. Standardize tool interfaces (MCP/A2A): framework-agnostic tool definitions
8. Standardize data formats: embeddings, vector schemas, metadata schemas
9. Plan migration sequence: low-risk systems first, high-impact last
10. Set up dual-run infrastructure: parallel old + new with traffic splitting
11. Execute cloud migration: re-platform with zero downtime (canary/blue-green)
12. Execute model migration: prompt adaptation, eval suite, canary rollout
13. Execute vector index migration: re-index or transfer, verify retrieval quality
14. Execute data migration: checksums, row counts, quality verification
15. Run migration quality gate: same eval suite pre/post, require equal or better
16. Performance benchmark: latency, throughput, cost before vs after
17. Track feature parity: dashboard showing migrated vs remaining capabilities
18. Configure governance continuity: GAIF-4 metrics across old + new during dual-run
19. Plan sunset: timeline, dependency notification, final cutover date
20. Execute sunset: decommission old system, archive data, close accounts
*[Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
