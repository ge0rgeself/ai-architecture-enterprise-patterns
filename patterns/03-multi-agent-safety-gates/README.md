# Pattern 03: Multi-Agent Pipeline with Safety Gates

**Chain specialized LLM agents with safety checkpoints between stages. 6 variants covering every multi-agent orchestration topology.**

## Which Variant Should You Use?

| Your situation | Variant |
|---------------|---------|
| Sequential task decomposition | [Linear Chain](linear-chain/) |
| Tasks can run in parallel | [DAG Orchestration](dag-orchestration/) |
| Need supervisor to coordinate workers | [Hierarchical](hierarchical/) |
| High-stakes decisions need multiple opinions | [Consensus](consensus/) |
| Output must withstand adversarial challenge | [Adversarial Red/Blue](adversarial-red-blue/) |
| Some outputs need human approval | [Human-in-the-Loop](human-in-the-loop/) |

## Architecture

**Agent Configuration (offline):** Agent Definitions, Tool Registry, Safety Rules, Permission Boundaries

**Execution Pipeline (online):** Request -> Agent -> Safety Gate -> Agent -> Safety Gate -> ... -> Final Validation -> Response

**Cross-cutting:** Agent Governance, Pipeline Observability

## Platform Mapping

| Component | Azure | AWS | GCP | Databricks | Open Source |
|-----------|-------|-----|-----|------------|-------------|
| Agent Framework | Semantic Kernel | Bedrock Agents | Agent Builder | Mosaic AI Agents | LangGraph / CrewAI |
| Safety Gates | Content Safety | Bedrock Guardrails | Model Armor | Mosaic GW Guardrails | NeMo Guardrails |
| Tool Protocol | Function Calling | Bedrock Actions | Extensions | Function Calling | MCP / A2A |
| Orchestration | Azure AI Agent Service | Step Functions | Vertex AI Pipelines | Databricks Workflows | LangGraph |
| Tracing | App Insights | X-Ray | Cloud Trace | MLflow Tracing | OpenTelemetry |

*Governance: [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
