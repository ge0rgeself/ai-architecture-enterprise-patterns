# Variant: AWS Native

**Full AWS ecosystem. API Gateway + Amazon Bedrock + Guardrails + IAM.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/aws-native/index.html)**

Five scenarios: RAG query (Kendra + Bedrock), ML inference (SageMaker), agentic workflow (Bedrock Agents), sensitive data (VPC endpoints), and Bedrock Agents orchestration.

## When to Use

**Use:** AWS shop with IAM. Need Claude/Llama via Bedrock. HIPAA eligible workloads. Bedrock Knowledge Bases for enterprise RAG. SageMaker for custom ML.

**Skip:** Need Azure-specific features (see azure-native). Need open-weight control (see databricks-native or open-source).

## Stack

| Component | AWS Service |
|-----------|------------|
| Gateway | API Gateway + Lambda authorizers |
| LLM | Amazon Bedrock (Claude, Llama, Titan) |
| Search | Amazon Kendra / OpenSearch |
| Guardrails | Guardrails for Amazon Bedrock |
| Auth | IAM Roles + Cognito |
| DLP | Amazon Macie |
| Monitoring | CloudWatch + X-Ray |
| IaC | CDK / CloudFormation |

Estimated cost: ~$850/month infrastructure.

## Files

| File | Purpose |
|------|---------|
| [index.html](index.html) | Interactive visualization ([demo](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/aws-native/index.html)) |
| [../DEPLOYMENT-GUIDE.md](../DEPLOYMENT-GUIDE.md) | Production docs |

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
