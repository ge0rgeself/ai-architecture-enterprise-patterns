# Variant: Swarm

**Many lightweight agents with no central coordinator. Emergent coordination through shared state and handoffs.**

## Live Demo
**[Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/03-multi-agent-safety-gates/swarm/index.html)**

Inspired by OpenAI Swarm pattern. Agents hand off to each other based on context. No supervisor, no central orchestrator. Scales horizontally.

**Use:** Large-scale document processing, distributed analysis, customer service routing, any task needing many specialized agents that self-coordinate.

**Skip:** Central orchestrator is needed (see hierarchical). Few agents are sufficient (see linear-chain).

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
