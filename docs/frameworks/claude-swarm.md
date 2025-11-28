---
layout: default
title: Claude Swarm
permalink: /frameworks/claude-swarm/
---

# Claude Swarm

**Multi-Agent Orchestrator** — 15x token efficiency via SwarmMemory.

## Quick Stats

| Metric | Value |
|--------|-------|
| **Category** | Orchestrator |
| **Version** | v2.3.0 |
| **SOLID Score** | 4.1/5.0 |
| **Production Score** | 80/100 |
| **Complexity** | MODERATE |
| **Stars** | 1,100+ |
| **Repository** | [upchunk/claude-swarm](https://github.com/upchunk/claude-swarm) |

## The Core Idea

Claude Swarm implements a single-process architecture with shared SwarmMemory, achieving 15x token efficiency compared to multi-process alternatives. All agents share context without the overhead of inter-process communication.

## Key Innovations

- **SwarmMemory:** Shared context achieving 15x efficiency
- **Single-Process:** No IPC overhead
- **Blueprint System:** Declarative swarm configuration
- **Ruby-Based:** Clean Ruby implementation

## Who Should Use This

**Perfect match:**
- Ruby environments
- Token-sensitive deployments
- Coordinated multi-agent tasks

**Probably not for you:**
- Non-Ruby projects
- Simple single-agent workflows

---

[← All Frameworks](/claude-framework-research/frameworks/)
