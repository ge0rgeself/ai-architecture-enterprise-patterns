# Variant: Reflection Loop

**Single agent reviews its own output iteratively until quality threshold is met.**

## Live Demo
**[Launch](https://aman210122.github.io/ai-architecture-enterprise-patterns/patterns/03-multi-agent-safety-gates/reflection-loop/index.html)**

Generate -> evaluate -> revise loop with max iteration limit. Not a chain of different agents but the same agent improving its own work.

**Use:** Code generation (generate -> test -> fix -> retest), writing refinement, mathematical proofs, any task where iterative improvement matters.

**Skip:** First attempt is good enough (see linear-chain). No iterative refinement needed.

*[AI Architecture Enterprise Patterns](https://github.com/aman210122/ai-architecture-enterprise-patterns) | Designed by [Aman Sharma](https://linkedin.com/in/amansharmaarchitect)*
