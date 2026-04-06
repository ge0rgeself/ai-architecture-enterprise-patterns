# Pattern 06: Governance-as-Architecture
**Governance wraps AROUND the AI system. 15 variants. Define, Assess, Enforce, Measure, Report. Not a PDF, embedded in architecture.**

Unique layout: U-shape governance wrapper with dashed boundary. Left column (pre-request: Define + Assess), center (AI System under governance), right column (runtime: Enforce + Measure), bottom (Report spanning full width). BSC 7-phase lifecycle bar.

| Governance Phase | Variant | When to Use |
|-----------------|---------|-------------|
| 4-tier risk system | [Risk Classification](risk-classification/) | Default. Classify every AI system by risk tier. |
| OPA/Rego rules | [Policy-as-Code](policy-as-code/) | Express policies as executable code, not documents. |
| GDPR/CCPA consent | [Consent Management](consent-management/) | Track user opt-in/out for AI processing. |
| Fairness testing | [Bias Testing](bias-testing/) | Demographic parity, equalized odds testing. |
| Attribution maps | [Explainability](explainability/) | Why did the AI say this? Audit trail. |
| Approval gates | [Human Oversight](human-oversight/) | Configurable human review per risk tier. |
| Model documentation | [Model Cards](model-cards/) | Standardized model capability/limitation docs. |
| Committee review | [Responsible AI Review](responsible-ai-review/) | Cross-functional committee for high-risk systems. |
| Training data audit | [Data Governance](data-governance/) | Data lineage, quality, consent for AI training. |
| EU AI Act, NIST, HIPAA | [Regulatory Mapping](regulatory-mapping/) | Map systems to applicable regulations. |
| CISO/CTO view | [Governance Dashboard](governance-dashboard/) | Real-time GAIF-4 across all systems. |
| Hallucination spike | [Incident Response](incident-response/) | AI-specific incident playbooks. |
| Unauthorized AI | [Shadow AI Detection](shadow-ai-detection/) | Detect unregistered AI API calls. |
| Third-party AI | [Vendor Governance](vendor-governance/) | Vendor risk assessment, BAA verification. |
| Automated checks | [Continuous Compliance](continuous-compliance/) | Policies validated continuously, not just at deploy. |

## Research Connection
- GAIF v1.0 (Zenodo DOI: 10.5281/zenodo.19341015): T1PR, CFR, EMR, GDR metrics
- BSC 7-phase governance lifecycle: Intake, Assess, Design, Build, Deploy, Monitor, Retire
- NIST AI RMF: MAP, MEASURE, MANAGE, GOVERN functions mapped to phases
- GDR paper submitted to IEEE Software: continuous governance decay measurement

*[GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
