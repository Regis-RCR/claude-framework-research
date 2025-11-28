---
layout: default
title: Claude Squad
permalink: /frameworks/claude-squad/
---

# Claude Squad

**Multi-Agent Orchestrator** — Isolation done right.

## Quick Stats

| Metric | Value |
|--------|-------|
| **Category** | Orchestrator |
| **Version** | v1.0.13 |
| **SOLID Score** | 4.0/5.0 |
| **Production Score** | 68/100 |
| **Complexity** | MODERATE |
| **Stars** | 5,100+ |
| **Repository** | [smtg-ai/claude-squad](https://github.com/smtg-ai/claude-squad) |

## The Core Idea

Here's a radical thought: what if agents just... never talked to each other?

Claude Squad takes the simplest possible approach to multi-agent orchestration. Each agent gets its own git worktree—a completely separate filesystem sandbox. No coordination protocols. No shared state. No message passing. Just parallel execution with standard git merge at the end.

The result? A **mathematical guarantee** against merge conflicts. Not "usually works." Not "careful orchestration." Mathematical certainty.

## Architecture

```
Main Repository
    ↓
Git Worktrees (per agent)
    ↓
Isolated Agent Sessions
    ↓
Standard Git Merge
```

**What you get:**
- No-communication architecture (feature, not bug)
- Daemon polling for unattended operation
- Agent-agnostic—works with Claude, Aider, Codex, Gemini
- Zero configuration. Really.

## Who Should Use This

**Perfect match:**
- Parallelizable tasks (independent features, batch bug fixes)
- Large refactoring campaigns
- Terminal-first workflows
- Developers wanting maximum throughput without complexity

**Probably not for you:**
- Workflows where agents need to talk to each other
- Simple sequential tasks (the overhead isn't worth it)
- Windows native dev (tmux dependency)
- Highly regulated environments needing audit trails

## SOLID Analysis

| Principle | Score | Notes |
|-----------|-------|-------|
| Single Responsibility | 4.0/5 | Tasks stay isolated |
| Open-Closed | 3.5/5 | Limited extension points |
| Liskov Substitution | 3.5/5 | Agents are swappable |
| Interface Segregation | 3.5/5 | CLI-focused, which works |
| Dependency Inversion | 3.5/5 | Git provides the abstraction |

## Production Readiness

- **Reliability:** 80/100 — Stable, actively maintained
- **Observability:** 75/100 — Session logging covers the basics
- **Security:** 75/100 — Standard git security model
- **Performance:** 85/100 — Minimal orchestration overhead
- **Maintainability:** 80/100 — Clean Go codebase

## Ecosystem

- **Coordination alternative:** [Claude Flow](/claude-framework-research/frameworks/claude-flow/) (Queen-Worker, alpha)
- **Memory-efficient:** [Claude Swarm](/claude-framework-research/frameworks/claude-swarm/) (SwarmMemory, 15x token efficiency)
- **Good pairing:** [BMAD Method](/claude-framework-research/frameworks/bmad-method/) (for planning before parallel execution)

---

[← All Frameworks](/claude-framework-research/frameworks/) | [View Full Analysis](https://github.com/Regis-RCR/claude-framework-research/blob/main/research-v2/analysis/claude-squad.md)
