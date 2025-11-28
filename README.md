# Claude Code Framework Research

Independent analysis of AI-assisted development frameworks built on Claude Code and the Claude Agent SDK.

## What This Research Covers

Twenty-one frameworks analyzed across four categories—methodology, orchestration, domain-specific, and specialty. Each framework evaluated using consistent criteria: architecture quality (SOLID principles), production readiness, and practical adoption considerations.

## Framework Overview

| Category | Count | Avg SOLID | Avg Production |
|----------|-------|-----------|----------------|
| Methodology | 11 | 3.98/5.0 | 69.5/100 |
| Orchestrator | 6 | 4.22/5.0 | 75.0/100 |
| Domain-Specific | 2 | 3.85/5.0 | 74.5/100 |
| Specialty | 2 | 3.90/5.0 | 76.5/100 |

### Top Frameworks by SOLID Score

| Framework | Category | SOLID | Production |
|-----------|----------|-------|------------|
| [Claude Code by Agents](https://regis-rcr.github.io/claude-framework-research/frameworks/claude-code-by-agents/) | Orchestrator | 4.5/5.0 | 69/100 |
| [BMAD Method](https://regis-rcr.github.io/claude-framework-research/frameworks/bmad-method/) | Methodology | 4.4/5.0 | 71/100 |
| [SystemPrompt Orchestrator](https://regis-rcr.github.io/claude-framework-research/frameworks/systemprompt-orchestrator/) | Orchestrator | 4.3/5.0 | 67/100 |
| [Claude Task Master](https://regis-rcr.github.io/claude-framework-research/frameworks/claude-task-master/) | Orchestrator | 4.2/5.0 | 83/100 |
| [RIPER-5](https://regis-rcr.github.io/claude-framework-research/frameworks/riper-5/) | Methodology | 4.2/5.0 | 72/100 |

### Top Frameworks by Production Score

| Framework | Category | SOLID | Production |
|-----------|----------|-------|------------|
| [Claude Task Master](https://regis-rcr.github.io/claude-framework-research/frameworks/claude-task-master/) | Orchestrator | 4.2/5.0 | 83/100 |
| [wshobson-agents](https://regis-rcr.github.io/claude-framework-research/frameworks/wshobson-agents/) | Orchestrator | 4.2/5.0 | 83/100 |
| [ClaudeKit](https://regis-rcr.github.io/claude-framework-research/frameworks/claudekit/) | Domain-Specific | 4.0/5.0 | 81/100 |
| [Claude Swarm](https://regis-rcr.github.io/claude-framework-research/frameworks/claude-swarm/) | Orchestrator | 4.1/5.0 | 80/100 |
| [MoAI-ADK](https://regis-rcr.github.io/claude-framework-research/frameworks/moai-adk/) | Specialty | 3.8/5.0 | 79/100 |

## Key Findings

**Complexity doesn't guarantee quality.** RIPER-5's five-phase protocol (Lightweight) achieves SOLID 4.2—matching frameworks with 10x the complexity. Focused design beats sprawling complexity.

**Orchestrators set the quality bar.** Average SOLID of 4.22 across orchestrator category—highest of any category. Parallel agent coordination demands good architecture.

**Production readiness varies widely.** Scores range from 52 to 83. Choose based on your reliability requirements, not just architecture scores.

## Documentation

Full analysis with detailed comparisons and the Super-Hero Framework vision:

**[View Complete Research →](https://regis-rcr.github.io/claude-framework-research/)**

## Methodology

Each framework evaluated through:
- Repository analysis (architecture, patterns, code quality)
- Documentation review (completeness, accuracy, maintenance)
- SOLID principles scoring (1-5 scale across five dimensions)
- Production readiness assessment (100-point composite score)
- Community health metrics (activity, responsiveness, adoption)

## License

MIT License - Copyright (c) 2025 Regis RCR

See [LICENSE](LICENSE) for details.

---

*Last updated: 2025-11-28*
