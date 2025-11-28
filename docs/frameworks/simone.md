---
layout: default
title: Simone
permalink: /frameworks/simone/
---

# Simone

**Context Management Framework** — Fresh starts, every time.

## Quick Stats

| Metric | Value |
|--------|-------|
| **Category** | Methodology |
| **Version** | MCP v0.4.0 |
| **SOLID Score** | 3.6/5.0 |
| **Production Score** | 63/100 |
| **Complexity** | STANDARD |
| **Stars** | 511 |
| **Repository** | [Helmi/claude-simone](https://github.com/Helmi/claude-simone) |

## The Problem It Solves

Context decay. You've felt it—the AI gets less useful as conversations stretch. Context windows fill up with stale information. Responses degrade.

Simone's answer: don't fight it. Start fresh every time, but inject the context that matters through templates.

Each task begins clean. Handlebars templates pull in project knowledge, architectural decisions, relevant history. Fresh context, not polluted context.

## Architecture

```
Task Request → Template Selection → Context Injection
      ↓
Handlebars Rendering → Prompt Generation → Claude Execution
      ↓
Activity Logging (SQLite) → GitHub Sync
```

**Task hierarchy:**
- Milestones (project phases)
- Sprints (work batches)
- Tasks (atomic units)

GitHub-native. Issues, Milestones, Projects integrate directly. Dual implementation: Legacy prompts or MCP integration.

## The Important Caveat

Development paused in August 2024.

That's not hidden in the fine print—it's reflected directly in the 63/100 production score. The 55/100 reliability sub-score tells the same story.

If you're evaluating for production use, this matters.

## Who Should Consider This

**Potentially good fit:**
- GitHub-native teams (Issues, Milestones, Projects)
- Long-term projects fighting context decay
- Teams wanting hierarchical task management
- MCP-compatible environments

**Probably not:**
- Non-GitHub teams (requires GitHub for full value)
- Quick prototypes (<2 weeks)
- Production-critical systems
- Teams uncomfortable with paused development

## SOLID Analysis

| Principle | Score | Notes |
|-----------|-------|-------|
| Single Responsibility | 4.0/5 | Tasks have single objectives |
| Open-Closed | 3.5/5 | Templates are extensible |
| Liskov Substitution | 3.0/5 | Legacy/MCP aren't interchangeable |
| Interface Segregation | 3.5/5 | MCP tools reasonably focused |
| Dependency Inversion | 4.0/5 | Template system is abstracted |

The 3.0 on Liskov reflects a real architectural limitation: you pick Legacy or MCP, and switching isn't trivial.

## Production Readiness

- **Reliability:** 55/100 — Development paused Aug 2024
- **Observability:** 65/100 — SQLite activity logging
- **Security:** 60/100 — GitHub OAuth integration
- **Performance:** 70/100 — Lightweight TypeScript
- **Maintainability:** 65/100 — TypeScript, ESLint configured

## Alternatives

- **More comprehensive:** [BMAD Method](/claude-framework-research/frameworks/bmad-method/) (active development, more features)
- **Simpler:** [RIPER-5](/claude-framework-research/frameworks/riper-5/) (no tooling dependencies)

---

[← All Frameworks](/claude-framework-research/frameworks/) | [View Full Analysis](https://github.com/Regis-RCR/claude-framework-research/blob/main/research-v2/analysis/simone.md)
