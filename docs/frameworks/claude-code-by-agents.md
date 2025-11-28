---
layout: default
title: Claude Code by Agents
permalink: /frameworks/claude-code-by-agents/
---

# Claude Code by Agents

**Multi-Agent Orchestrator** — Hybrid local/remote agent coordination with intelligent routing.

## Quick Stats

| Metric | Value |
|--------|-------|
| **Category** | Orchestrator |
| **Version** | v0.1.41 |
| **SOLID Score** | 4.5/5.0 |
| **Production Score** | 69/100 |
| **Complexity** | MODERATE |
| **Stars** | 679 |
| **Repository** | [baryhuang/claude-code-by-agents](https://github.com/baryhuang/claude-code-by-agents) |

## The Core Idea

Claude Code by Agents transforms Claude Code into a distributed collaborative development environment. Multiple specialized agents coordinate through a hub-and-spoke architecture with intelligent task decomposition and dependency management.

## Key Innovations

- **@Mention Routing:** Direct agent targeting bypasses orchestration for simple tasks
- **Hybrid Deployment:** Mix local and remote agents seamlessly
- **OAuth Integration:** No API keys required, leverages Claude CLI auth
- **Desktop Application:** Polished Electron app for Windows/macOS/Linux

## Who Should Use This

**Perfect match:**
- Teams needing parallel development across specializations
- Projects requiring coordinated multi-agent workflows
- Environments mixing local and cloud resources

**Probably not for you:**
- Simple single-agent workflows
- Security-sensitive environments (HTTP between agents)

---

[← All Frameworks](/claude-framework-research/frameworks/)
