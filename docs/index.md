---
layout: default
title: Home
nav_next:
  url: /frameworks/
  label: "View All Frameworks"
---

# Claude Code Framework Research

*What happens when you throw the scientific method at AI-assisted development?*

We analyzed **21 frameworks** designed to make Claude Code work better for professional software development. Not marketing claims—actual architecture reviews, SOLID principle assessments, and production readiness scores. Here's what we found.

{% include search.html %}

## The Corpus at a Glance

| Category | Count | Avg SOLID | Avg Production |
|----------|-------|-----------|----------------|
| Methodology | 11 | 3.98/5.0 | 69.4/100 |
| Orchestrator | 6 | 4.22/5.0 | 75.0/100 |
| Domain-Specific | 2 | 3.85/5.0 | 74.5/100 |
| Specialty | 2 | 3.90/5.0 | 76.5/100 |

## Browse by Category

### Methodology
*How you structure the development process*

- **[BMAD Method](/claude-framework-research/frameworks/bmad-method/)** — The heavyweight champion. 19 agents, 50+ workflows, enterprise-grade everything. SOLID 4.4, but expect a learning curve.
- **[Task Master](/claude-framework-research/frameworks/taskmaster-mcp/)** — De facto standard for structured project planning. 23.9k stars, PRD-to-task decomposition. SOLID 4.2.
- **[SuperClaude](/claude-framework-research/frameworks/superclaude/)** — Behavioral injection approach with 16 cognitive personas. Solid token optimization if you're watching costs.
- **[RIPER-5](/claude-framework-research/frameworks/riper-5/)** — Dead simple (5 phases, zero tooling) yet scores SOLID 4.2. Proves you don't need complexity to get quality.
- **[Claude Code Dev Kit](/claude-framework-research/frameworks/claude-code-dev-kit/)** — Structured project scaffolding and workflow optimization. SOLID 4.2, 1.2k stars.
- **[AB Method](/claude-framework-research/frameworks/ab-method/)** — Incremental development methodology with strong documentation focus. SOLID 3.9.
- **[CCPM](/claude-framework-research/frameworks/ccpm/)** — Claude Code Project Manager for structured project workflows. SOLID 3.7.
- **[ContextKit](/claude-framework-research/frameworks/contextkit/)** — Context management and optimization toolkit. SOLID 3.8.
- **[Claude Code Heavy](/claude-framework-research/frameworks/claude-code-heavy/)** — Git worktree isolation for parallel research. SOLID 3.8.
- **[Simone](/claude-framework-research/frameworks/simone/)** — Tackles context decay with "fresh start" philosophy. Development paused since August 2024.
- **[NIOPD](/claude-framework-research/frameworks/niopd/)** — Product management focused methodology. SOLID 3.9.

### Orchestrator
*Running multiple AI agents in parallel*

- **[Claude Code by Agents](/claude-framework-research/frameworks/claude-code-by-agents/)** — Highest SOLID score (4.5) in corpus. Hybrid local/remote agent coordination with intelligent routing.
- **[SystemPrompt Orchestrator](/claude-framework-research/frameworks/systemprompt-orchestrator/)** — Multi-AI coordination for Claude and Gemini. SOLID 4.3.
- **[Claude Task Master](/claude-framework-research/frameworks/claude-task-master/)** — MCP-based task orchestration with 23.9k stars. SOLID 4.2, Production 83.
- **[wshobson/agents](/claude-framework-research/frameworks/wshobson-agents/)** — Agent library with strong production score (83). SOLID 4.2.
- **[Claude Swarm](/claude-framework-research/frameworks/claude-swarm/)** — SwarmMemory for 15x token efficiency. Single-process architecture. SOLID 4.1, Production 80.
- **[Claude Squad](/claude-framework-research/frameworks/claude-squad/)** — Git worktree isolation means mathematically guaranteed conflict-free parallel execution. Production score 68.

### Domain-Specific
*Deep expertise in one technology stack*

- **[Claude on Rails](/claude-framework-research/frameworks/claude-on-rails/)** — Built by Obie Fernandez. Seven Rails-specific agents that actually know Rails conventions.
- **[ClaudeKit](/claude-framework-research/frameworks/claudekit/)** — TypeScript/JavaScript toolkit with 195+ security patterns. Highest production score (81) in this category.

### Specialty
*Unique approaches and specialized tools*

- **[Crystal](/claude-framework-research/frameworks/crystal/)** — Desktop-focused development toolkit. SOLID 4.0, Production 74.
- **[Moai ADK](/claude-framework-research/frameworks/moai-adk/)** — Agentic development kit with strong production readiness (79). SOLID 3.8.

## What We Learned

A few findings challenged our assumptions:

**Simplicity wins more often than you'd think.** RIPER-5's minimal approach (just 5 phases, copy-paste to use) achieved SOLID 4.2—matching frameworks with 10x the complexity.

**GitHub stars tell you about reach, not quality.** Task Master has 23.9k stars with SOLID 4.2. Claude Code by Agents has 679 stars with SOLID 4.5. Community size measures how many people *found* something, not how good it is.

**Orchestrators set the quality bar.** Average SOLID of 4.22 across the orchestrator category—highest of any category. Parallel agent coordination demands good architecture.

**Production readiness varies wildly.** Scores range from 52 to 83. If you're choosing a framework for serious work, look beyond SOLID scores.

## Dig Deeper

- [Methodology Comparison](/claude-framework-research/comparisons/methodology/) — Multi-way analysis of development methodologies
- [Orchestrator Comparison](/claude-framework-research/comparisons/orchestrator/) — Isolation vs Coordination approaches
- [Domain-Specific Comparison](/claude-framework-research/comparisons/domain-specific/) — Rails vs TypeScript specialists
- [Full Synthesis](/claude-framework-research/synthesis/) — Complete cross-framework analysis

## Building Something Better

What if you could combine the best patterns from all 21 frameworks?

[Explore our Super-Hero Framework vision](/claude-framework-research/super-hero/)—a blueprint for the ideal AI-assisted development framework. Document sharding meets behavioral constraints. Git worktree isolation meets fresh-start context. Security patterns meet domain expertise.

Not theoretical. Each pattern is proven in production. The innovation is integration, not invention.

## How We Did This

Every framework went through the same process:
- Architecture deep-dive from primary sources (repos, docs, code)
- SOLID principles assessment with justification for each score
- Production readiness evaluation across 5 dimensions
- Standardized analysis covering 12 core sections plus category-specific extensions

No hand-waving. No "it seems good." Evidence or it didn't happen.

---

*Last updated: 2025-11-28 · [View on GitHub](https://github.com/Regis-RCR/claude-framework-research)*

{% include page-navigation.html %}
