# Variant: Snowflake Native

**Snowflake Cortex + Snowpark + Arctic + Streamlit. AI runs where your data lives.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/snowflake-native/index.html)**

Five scenarios: RAG query (Cortex Search), ML inference (Snowpark ML), agentic workflow, sensitive data (role-based security), and Streamlit app delivery.

## When to Use

**Use:** Data already lives in Snowflake. Want SQL-based AI (call LLMs with SQL functions). Streamlit for instant internal tools. Zero data movement. Column-level security + row access policies.

**Skip:** Need GPT-4o reasoning (see azure-native). Data outside Snowflake (see multi-platform).

## Stack

| Component | Snowflake Service |
|-----------|------------------|
| Gateway | Cortex Gateway |
| Models | Arctic, Mistral Large, Llama (via Cortex) |
| Search | Cortex Search |
| Guardrails | Cortex Guard |
| Auth | Snowflake Roles + PrivateLink |
| Monitoring | Account Usage + Event Tables |

Estimated cost: ~$700/month (Snowflake credits).

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
