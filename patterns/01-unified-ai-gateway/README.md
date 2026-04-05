# Pattern 01: Unified AI Gateway

**Route all LLM and ML traffic through a single governance-aware control plane.**

---

## The Problem

Teams independently call different model providers without centralized governance. This creates ungoverned data flows, invisible cost accumulation, no audit trail, inconsistent safety policies, and vendor lock-in.

## The Solution

A centralized AI gateway intercepts all model requests and responses, applying governance policies, routing intelligently, and maintaining a complete audit trail.

---

## Which Variant Should You Use?

### By cloud provider:
| Your stack | Variant |
|-----------|---------|
| Microsoft / Azure | [Azure Native](azure-native/) |
| AWS | AWS Native (coming soon) |
| Google Cloud | GCP Native (coming soon) |
| Databricks | [Databricks Native](databricks-native/) |
| Snowflake | Snowflake Native (coming soon) |
| Multiple platforms | [Multi-Platform](multi-platform/) |
| Multiple clouds | [Multi-Cloud](multi-cloud/) |
| Self-hosted / air-gap | [Open Source](open-source/) |

### By data sensitivity:
| Situation | Variant |
|-----------|---------|
| Mixed cloud + on-prem | Multi-Platform or Open Source |
| All cloud (with BAA/DPA) | Azure Native or Databricks Native |
| Nothing leaves your network | Open Source |

### By budget:
| Situation | Monthly cost | Variant |
|-----------|-------------|---------|
| Large team, multi-platform | ~$1,400 | Multi-Platform |
| Medium team, single cloud | ~$800-900 | Azure or Databricks Native |
| Multi-cloud | ~$1,200 | Multi-Cloud |
| Cost is primary concern | ~$400 | Open Source |

---

## Variant Comparison

| Variant | Providers | Gateway | Complexity | Cost/mo |
|---------|-----------|---------|-----------|---------|
| Azure Native | Azure OpenAI (GPT-4o, 4.1) | Azure APIM | Medium | ~$900 |
| Databricks Native | DBRX, Llama, Mixtral | Mosaic AI GW | Medium | ~$800 |
| Multi-Platform | Databricks + Azure + Snowflake | Mosaic AI GW | High | ~$1,400 |
| Multi-Cloud | Azure + AWS + GCP | Kong | High | ~$1,200 |
| Open Source | Llama, Mistral (self-hosted) | LiteLLM | Medium | ~$400 |

---

## Architecture (10 sections, 2 pipelines)

**Build Pipeline:** Data Sources -> Data Prep -> Develop & Evaluate -> Catalog & Registry -> Context Delivery (CSP)

**Runtime Pipeline:** Search & Retrieval -> AI Gateway -> Prompt Processing -> Serving -> Consumption

**Cross-cutting:** Governance, Platform Tenancy, Observability & FinOps, Deployment & Infrastructure

---

## GAIF-4 Governance Metrics

| Metric | Threshold (safe) | Threshold (critical) |
|--------|-----------------|---------------------|
| T1PR (Type-1 Pass Rate) | < 0.05 | > 0.15 |
| CFR (Compliance Failure) | 0.00 | > 0.01 |
| EMR (Emergent Misinformation) | 0.00 | > 0.05 |
| GDR (Governance Decay) | < 0.03 | > 0.05 |

---

## Files

| File | Purpose |
|------|---------|
| [DEPLOYMENT-GUIDE.md](DEPLOYMENT-GUIDE.md) | Production deployment documentation |
| [azure-native/](azure-native/) | Azure APIM + OpenAI variant |
| [databricks-native/](databricks-native/) | Mosaic AI GW + FMAPI variant |
| [multi-platform/](multi-platform/) | Databricks + Azure + Snowflake variant |
| [multi-cloud/](multi-cloud/) | Kong + Azure + AWS + GCP variant |
| [open-source/](open-source/) | LiteLLM + vLLM self-hosted variant |

---

*Governance: [GAIF Observatory](https://github.com/aman210122/gaif-governance-observatory) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
