# Pattern 03: Multi-Agent Pipeline with Safety Gates

**Chain specialized LLM agents with safety checkpoints. 10 variants covering every multi-agent orchestration topology.**

## Which Variant Should You Use?

| Your situation | Variant |
|---------------|---------|
| Sequential task decomposition | [Linear Chain](linear-chain/) |
| Tasks can run in parallel | [DAG Orchestration](dag-orchestration/) |
| Supervisor coordinates workers | [Hierarchical](hierarchical/) |
| High-stakes decisions, multiple opinions | [Consensus](consensus/) |
| Output must withstand challenge | [Adversarial Red/Blue](adversarial-red-blue/) |
| Human approval needed per risk tier | [Human-in-the-Loop](human-in-the-loop/) |
| Decisions need for/against arguments | [Debate](debate/) |
| Iterative self-improvement loop | [Reflection Loop](reflection-loop/) |
| Many agents, no central coordinator | [Swarm](swarm/) |
| Non-blocking safety observation | [Parallel Monitor](parallel-monitor/) |

## Platform Mapping

| Component | Azure | AWS | GCP | Databricks | Open Source |
|-----------|-------|-----|-----|------------|-------------|
| Agent Framework | Semantic Kernel | Bedrock Agents | Agent Builder | Mosaic AI Agents | LangGraph / CrewAI |
| Safety Gates | Content Safety | Bedrock Guardrails | Model Armor | Mosaic GW | NeMo Guardrails |
| Tool Protocol | Function Calling | Bedrock Actions | Extensions | Function Calling | MCP / A2A |
| Orchestration | AI Agent Service | Step Functions | Vertex Pipelines | Workflows | LangGraph |
| Tracing | App Insights | X-Ray | Cloud Trace | MLflow Tracing | OpenTelemetry |

*Governance: [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
