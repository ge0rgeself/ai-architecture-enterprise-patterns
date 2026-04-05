# Variant: Parallel Monitor

**Dedicated safety agent runs continuously alongside the pipeline, observing all outputs in real-time.**

## Live Demo
**[Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/03-multi-agent-safety-gates/parallel-monitor/index.html)**

Different from safety gates: the monitor does not block the pipeline. It observes, flags, and can escalate without adding latency. Only overrides in critical situations.

**Use:** Compliance monitoring without blocking throughput, real-time PHI detection, continuous audit during inference, latency-sensitive pipelines that cannot afford gate delays.

**Skip:** Blocking gates are acceptable (see linear-chain). Latency from gates is fine (see any gate-based variant).

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
