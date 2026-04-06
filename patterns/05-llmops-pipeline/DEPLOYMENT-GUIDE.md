# Deployment Guide: LLMOps Pipeline
## Prerequisites: Git repo for prompts, eval framework, model registry, deployment target
## Steps
1. Set up prompt versioning: git repo with system prompts, few-shot examples, templates
2. Build eval suite: golden dataset (100+ test cases), quality rubric, adversarial cases
3. Configure CI pipeline: eval runs on every PR, quality gate blocks merge if score < 0.85
4. Deploy model registry: MLflow / AI Foundry / Bedrock model catalog
5. Register prompt-model combinations: version, eval results, approval chain
6. Configure canary deployment: 10% traffic split, quality comparison, auto-promote/reject
7. Set up monitoring: quality sampling (5%), latency percentiles, cost per query
8. Configure drift detection: 7-day rolling average, alert on downward trend
9. Build rollback capability: instant switch to previous version, auto-trigger on quality drop
10. Set up A/B testing framework: traffic split, significance testing, duration planning
11. Configure cost optimization: route by complexity, cache repeated queries
12. GAIF-4: T1PR on bad prompts in production, GDR on process decay
*[Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
