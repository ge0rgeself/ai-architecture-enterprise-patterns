# Pattern 05: LLMOps Lifecycle Pipeline
**Development column + Model Registry hub + Production column. 12 variants. Prompt versioning, eval gates, canary deploy, drift detection, cost optimization.**

Unique layout: develop phases flow down on the left, register in the central hub, deploy and monitor flow down on the right, feedback loops back up to development.

| Lifecycle Area | Variant | When to Use |
|----------------|---------|-------------|
| Prompt management | [Prompt Versioning](prompt-versioning/) | Default. Git-backed, PR review, semantic versioning. |
| Model comparison | [Model Selection](model-selection/) | Choosing between providers/models for a use case. |
| Quality gates in CI | [Eval-Driven Development](eval-driven-development/) | Every prompt change must pass eval before merge. |
| Gradual rollout | [Canary Deployment](canary-deployment/) | Deploy to 10% traffic, compare, promote or reject. |
| Statistical comparison | [A/B Testing](ab-testing/) | Comparing prompt/model variants with significance. |
| Instant revert | [Rollback Strategy](rollback-strategy/) | Auto-rollback on quality drop. |
| Centralized prompts | [Prompt Registry](prompt-registry/) | All prompts in one searchable, versioned store. |
| Production quality | [Model Monitoring](model-monitoring/) | Continuous quality, latency, cost tracking. |
| Quality degradation | [Drift Detection](drift-detection/) | Detect model provider silent updates. |
| Cost reduction | [Cost Optimization](cost-optimization/) | Route simple queries to cheap models. |
| Gradual enable | [Feature Flags](feature-flags/) | Enable features per user segment. |
| Zero-downtime swap | [Blue/Green Deployment](blue-green-deployment/) | Two environments, instant switch. |

*[GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
