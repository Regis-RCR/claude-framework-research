---
layout: default
title: Comparisons
permalink: /comparisons/
nav_prev:
  url: /frameworks/
  label: "All Frameworks"
nav_next:
  url: /synthesis/
  label: "Full Synthesis"
---

# Framework Comparisons

Head-to-head analysis within each category. Pick your domain, find your framework.

## By Category

### [Methodology (11-way)](/claude-framework-research/comparisons/methodology/)
**BMAD Method, Task Master MCP, RIPER-5, Claude Code Dev Kit, SuperClaude, AB Method, NioPD, ContextKit, Claude Code Heavy, CCPM, Simone**

Eleven approaches spanning LIGHTWEIGHT to HEAVY complexity. The interesting finding? Simplicity doesn't mean lower quality.

### [Orchestrator (7-way)](/claude-framework-research/comparisons/orchestrator/)
**Claude Code by Agents, SystemPrompt Orchestrator, Claude Task Master, wshobson-agents, Claude Swarm, Claude Squad, Claude Flow**

Seven frameworks with diverse approaches: hybrid routing, multi-AI coordination, MCP-based orchestration, git worktree isolation, and Queen-Worker coordination. Highest average SOLID in the corpus.

### [Domain-Specific (2-way)](/claude-framework-research/comparisons/domain-specific/)
**Claude on Rails vs ClaudeKit**

Rails specialists versus TypeScript specialists. Different stacks, similar approaches, surprisingly different outcomes.

## Quick Comparison (Top 10)

| Framework | Category | SOLID | Production | Sweet Spot |
|-----------|----------|-------|------------|------------|
| Claude Code by Agents | Orchestrator | 4.5/5.0 | 69/100 | Hybrid routing |
| BMAD Method | Methodology | 4.4/5.0 | 71/100 | Enterprise governance |
| SystemPrompt Orchestrator | Orchestrator | 4.3/5.0 | 67/100 | Multi-AI coordination |
| Claude Task Master | Orchestrator | 4.2/5.0 | 83/100 | MCP task orchestration |
| wshobson-agents | Orchestrator | 4.2/5.0 | 83/100 | Agent marketplace |
| RIPER-5 | Methodology | 4.2/5.0 | 72/100 | Immediate adoption |
| Claude Swarm | Orchestrator | 4.1/5.0 | 80/100 | Token efficiency |
| SuperClaude | Methodology | 4.1/5.0 | 73/100 | Token optimization |
| ClaudeKit | Domain-Specific | 4.0/5.0 | 81/100 | Secure TypeScript |
| Claude Squad | Orchestrator | 4.0/5.0 | 68/100 | Git worktree isolation |

## Decision Tree

```
Starting point: Need AI-assisted development?
│
├── Need process structure? → METHODOLOGY (11 options)
│   ├── Enterprise governance? → BMAD Method
│   ├── PRD decomposition? → Task Master MCP
│   ├── Token optimization? → SuperClaude
│   ├── Quick adoption? → RIPER-5
│   └── Context management? → ContextKit
│
├── Need parallel execution? → ORCHESTRATOR (7 options)
│   ├── Best architecture? → Claude Code by Agents
│   ├── Production stability? → Claude Task Master / wshobson-agents
│   ├── Token efficiency? → Claude Swarm
│   ├── Conflict-free parallel? → Claude Squad
│   └── Complex coordination? → Claude Flow (alpha)
│
└── Specific technology stack? → DOMAIN-SPECIFIC
    ├── Ruby on Rails? → Claude on Rails
    └── TypeScript/JavaScript? → ClaudeKit
```

## What We Learned

Three findings that challenged our assumptions:

1. **Complexity ≠ Quality** — RIPER-5 (LIGHTWEIGHT) achieves SOLID 4.2, matching Task Master MCP. Five phases with hard constraints compete with comprehensive tooling.

2. **Orchestrators Set the Bar** — Average SOLID of 4.22 across orchestrator category—highest of any category. Parallel agent coordination demands good architecture.

3. **Community ≠ Quality** — Smaller communities can produce high-quality frameworks. Claude Code by Agents (679 stars) achieves the highest SOLID (4.5) in the entire corpus.

---

{% include page-navigation.html %}
