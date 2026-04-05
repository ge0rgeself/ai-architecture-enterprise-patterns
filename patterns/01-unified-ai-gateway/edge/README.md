# Variant: Edge Gateway

**On-device or local server. Sub-50ms latency. Works offline.**

## Live Demo

**[Launch interactive visualization](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/01-unified-ai-gateway/edge/index.html)**

Five scenarios: RAG query (local), ML inference (on-device), agentic workflow, policy sync (cloud to device), and fully offline inference.

## When to Use

**Use:** Latency under 50ms is critical. Must work offline or with intermittent connectivity. Data cannot leave the device. IoT, mobile, field operations, manufacturing floors, retail stores, healthcare devices, military/defense.

**Skip:** Cloud latency is acceptable (see any cloud variant). Full model capability needed (see open-source).

## Stack

| Component | Tool |
|-----------|------|
| Gateway | Local proxy (cached policies) |
| Models | Phi-3-mini (3.8B), Gemma 2B, TinyLlama (1.1B) |
| Runtime | ONNX Runtime / llama.cpp |
| Vector DB | Local HNSW index |
| Guardrails | Cached blocklist + local filter |
| Policy sync | Cloud pull when online (24h offline validity) |
| Hardware | 8GB+ RAM device (Jetson, RPi 5, laptop, edge server) |

Estimated cost: ~$100-300/device (hardware amortized).

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
