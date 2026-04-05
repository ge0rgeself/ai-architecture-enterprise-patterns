# Pattern 04: Agentic AI with Tool Governance

**Governance on what agents can DO, not just what they say. 5 variants covering every tool integration protocol.**

## Which Variant Should You Use?

| Your situation | Variant |
|---------------|---------|
| Standardized tool servers with typed schemas | [MCP Protocol](mcp-protocol/) |
| Agent-to-agent collaboration across services | [A2A Protocol](a2a-protocol/) |
| Simplest tool integration, provider-native | [Function Calling](function-calling/) |
| Tools that chain other tools | [Compound Tools](compound-tools/) |
| Agent generates and runs code | [Sandboxed Execution](sandboxed-execution/) |

## Platform Mapping

| Component | Azure | AWS | GCP | Databricks | Open Source |
|-----------|-------|-----|-----|------------|-------------|
| Tool Framework | Semantic Kernel | Bedrock Actions | Vertex Extensions | Unity Catalog Functions | MCP SDK / LangChain |
| Execution | Azure Functions | Lambda | Cloud Functions | Serverless Compute | Docker containers |
| Auth | Managed Identity | IAM Roles | Service Accounts | Unity Catalog ACLs | Keycloak / OAuth |
| Sandbox | Container Apps | Fargate | Cloud Run | Cluster Policies | gVisor / Firecracker |
| Audit | App Insights | CloudTrail | Cloud Audit | MLflow | OpenTelemetry |

*Governance: [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
