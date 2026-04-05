# Pattern 09: AI Evaluation & Red Teaming

**Systematic AI quality and safety evaluation. 10 variants from automated adversarial testing to domain-specific clinical evaluation.**

## Which Variant Should You Use?

| Your situation | Variant |
|---------------|---------|
| Find vulnerabilities before production | [Automated Red Teaming](automated-red-teaming/) |
| RAG quality evaluation | [RAGAS Evaluation](ragas-evaluation/) |
| Scalable quality without human evaluators | [LLM-as-Judge](llm-as-judge/) |
| Gold standard with human raters | [Human Evaluation](human-eval/) |
| Pre-deployment safety certification | [Safety Benchmarking](safety-benchmarking/) |
| Ongoing production quality monitoring | [Continuous Evaluation](continuous-eval/) |
| Test against adversarial inputs | [Adversarial Robustness](adversarial-robustness/) |
| Systematic demographic bias testing | [Bias Evaluation](bias-evaluation/) |
| Catch degradation between versions | [Regression Testing](regression-testing/) |
| Healthcare/legal/finance-specific eval | [Domain-Specific](domain-specific-eval/) |

## Platform Mapping

| Component | Azure | AWS | GCP | Databricks | Open Source |
|-----------|-------|-----|-----|------------|-------------|
| Eval Framework | AI Foundry Eval | Bedrock Eval | Vertex Eval | MLflow Evaluate | RAGAS / DeepEval |
| Red Teaming | PyRIT | Custom | Custom | Custom | Garak / PyRIT |
| Safety Testing | Content Safety | Guardrails | Model Armor | Mosaic GW | NeMo Guardrails |
| Human Eval | Custom | SageMaker GT | Vertex Data Labeling | Custom | Label Studio |

*Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
