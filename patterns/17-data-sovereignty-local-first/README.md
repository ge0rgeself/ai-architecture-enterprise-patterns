# Pattern 17: Data Sovereignty and Local-First AI
**WHERE computation happens. 12 variants. On-premises, sovereign cloud, edge, air-gapped, hybrid inference.**

Info-Tech 2026: 72% of IT leaders cite data sovereignty as their top AI challenge. This pattern is about computation location, not data classification (that is Pattern 08).

| Sovereignty Model | Variant |
|------------------|---------|
| vLLM/Ollama on your hardware | [On-Premises Serving](on-premises-serving/) |
| Government/defense cloud | [Sovereign Cloud](sovereign-cloud/) |
| EU-only, US-only compute | [Geo-Fenced Compute](geo-fenced-compute/) |
| Latency at the edge | [Edge AI Inference](edge-ai-inference/) |
| No internet connection | [Air-Gapped Deployment](air-gapped-deployment/) |
| Sensitive local, rest in cloud | [Hybrid Inference](hybrid-inference/) |
| Move compute to data | [Data Gravity](data-gravity/) |
| Training on your hardware | [Local Fine-Tuning](local-fine-tuning/) |
| GDPR, PIPL, DPDP, state laws | [Cross-Border Controls](cross-border-controls/) |
| Self-hosted model control | [Private Model Hosting](private-model-hosting/) |
| TEE/enclave inference | [Confidential Computing](confidential-computing/) |
| Healthcare, defense, finance | [Regulated Industry](regulated-industry-deployment/) |

## Sovereignty Decision Matrix
| Data Sensitivity | Latency Need | Regulation | Recommended Model |
|-----------------|-------------|------------|-------------------|
| Public | Tolerant | None | Cloud inference |
| Internal | Tolerant | GDPR | Geo-fenced cloud |
| Confidential | Low | HIPAA | Sovereign cloud |
| Restricted | Ultra-low | Defense | Air-gapped on-prem |
| Mixed | Variable | Multi-reg | Hybrid inference |

*[GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
