# Pattern 08: Compliance-Aware Data Routing

**Data sensitivity drives model and provider selection. 10 variants covering every cloud, jurisdiction, and compliance model.**

## Which Variant Should You Use?

| Your situation | Variant |
|---------------|---------|
| Azure ecosystem (Purview + BAA) | [Azure Compliance](azure-compliance/) |
| AWS ecosystem (Macie + Bedrock) | [AWS Compliance](aws-compliance/) |
| GCP ecosystem (DLP API + VPC-SC) | [GCP Compliance](gcp-compliance/) |
| Multiple clouds, unified policy | [Multi-Cloud Compliance](multi-cloud-compliance/) |
| Air-gapped / government | [On-Prem Compliance](on-prem-compliance/) |
| Building the classification engine | [Sensitivity Classification](sensitivity-classification/) |
| EU/US/Asia data residency | [Data Residency Routing](data-residency-routing/) |
| GDPR consent-based decisions | [Consent-Based Routing](consent-based-routing/) |
| Sensitivity changes mid-pipeline | [Dynamic Reclassification](dynamic-reclassification/) |
| International data transfers | [Cross-Border Routing](cross-border-routing/) |

## Regulatory Mapping

| Regulation | Region | Key Routing Impact |
|-----------|--------|-------------------|
| HIPAA | US | PHI routes to BAA providers only |
| GDPR | EU | Consent determines processing, data stays in EU |
| PCI-DSS | Global | Card data to PCI-compliant endpoints |
| PIPL | China | Data stays in China unless explicit consent |
| DPDP | India | Data localization for certain categories |
| LGPD | Brazil | Similar to GDPR, Brazilian jurisdiction |
| FedRAMP | US Gov | FedRAMP-authorized providers only |

*Governance: [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
