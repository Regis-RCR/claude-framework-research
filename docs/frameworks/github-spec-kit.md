---
title: GitHub Spec-Kit
layout: default
parent: Frameworks
---

# GitHub Spec-Kit

<div class="framework-meta">
<strong>Version:</strong> 0.0.22 |
<strong>Repository:</strong> <a href="https://github.com/github/spec-kit">GitHub</a> |
<strong>License:</strong> MIT
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: cli, prompt-based</span>
<span class="badge badge-exec">exec: single-agent</span>
<span class="badge badge-function">function: dev-methodology</span>
<span class="badge badge-ecosystem">ecosystem: python</span>
<span class="badge badge-scope">scope: project-level</span>
<span class="badge badge-integration">integration: drop-in</span>
<span class="badge badge-user">user: solo-dev, team</span>
<span class="badge badge-complexity">complexity: medium</span>
<span class="badge badge-maturity">maturity: stable</span>
<span class="badge badge-community">community: established</span>
<span class="badge badge-maintenance">maintenance: active</span>
</div>

## Scores Summary

<div class="scores-grid">
<table>
<thead>
<tr><th colspan="2">SOLID Principles</th><th colspan="2">Production Ready</th></tr>
</thead>
<tbody>
<tr>
<td><strong>Overall</strong></td>
<td>4.3/5.0 ⭐⭐⭐⭐☆</td>
<td><strong>Overall</strong></td>
<td>78/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>4.5/5.0</td>
<td>Reliability</td>
<td>80</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>4.5/5.0</td>
<td>Observability</td>
<td>70</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>4.0/5.0</td>
<td>Security</td>
<td>82</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>4.5/5.0</td>
<td>Performance</td>
<td>85</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>4.0/5.0</td>
<td>Maintainability</td>
<td>73</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Specification-as-executable-artifact paradigm</li>
<li>Constitutional governance framework (9 articles)</li>
<li>Universal multi-AI compatibility (16+ agents)</li>
<li>Template-driven LLM constraint system</li>
<li>Slash command workflow orchestration (9 commands)</li>
<li>Dual-mode support (greenfield and brownfield)</li>
</ul>

## Best For

<ul class="compact-list">
<li>Enterprise software specification</li>
<li>Team-based AI-assisted development</li>
<li>Requirements-first development workflows</li>
<li>Complex project planning and documentation</li>
<li>Cross-team specification consistency</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Requires discipline to maintain specifications</li>
<li>Heavy upfront investment in spec creation</li>
<li>Not suitable for rapid prototyping</li>
<li>Template rigidity may not fit all projects</li>
<li>Python 3.11+ requirement limits some environments</li>
</ul>

---

## Full Analysis

# GitHub Spec-Kit - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-12-01
> - Analyst: Claude (via framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-research:framework-analyzer")
> - Template Version: 1.1
> - Category: methodology

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Architecture Overview](#2-architecture-overview)
3. [Core Components](#3-core-components)
4. [Design Patterns](#4-design-patterns)
5. [Strengths](#5-strengths)
6. [Limitations](#6-limitations)
7. [Production Readiness](#7-production-readiness)
8. [Comparative Analysis](#8-comparative-analysis)
9. [Integration Patterns](#9-integration-patterns)
10. [Best Practices](#10-best-practices)
11. [Configuration Reference](#11-configuration-reference)
12. [Recommendations](#12-recommendations)
X. [Workflow Definition](#x-workflow-definition)
Y. [Prompt Engineering](#y-prompt-engineering)
Z. [Guardrails and Quality](#z-guardrails-and-quality)

---

## 1. Executive Summary

GitHub Spec-Kit is an open-source toolkit that implements Spec-Driven Development (SDD), a methodology where specifications become executable artifacts that directly generate working implementations rather than merely guiding them. Developed and maintained by GitHub, Spec-Kit "flips the script" on traditional software development by treating specifications as first-class citizens that drive the entire development process.

**Key Value Proposition**: Transform vague feature descriptions into structured, validated specifications that can be executed consistently across 16+ AI coding assistants, ensuring reproducible and high-quality software development regardless of the underlying AI tool used.

The framework centers around the `specify` CLI tool and a set of slash commands (`/speckit.*`) that orchestrate the spec-driven workflow. Projects begin with a constitution that establishes governance principles, followed by specifications that define features, plans that detail technical implementation, and tasks that break work into actionable items.

**Core Innovation**: Unlike traditional methodologies where specifications are consumed and discarded, Spec-Kit specifications remain the source of truth throughout development. The constitution pattern borrowed from governance systems ensures all development decisions align with project principles, creating a self-reinforcing quality framework.

---

## 2. Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────┐
│                      SPEC-KIT ARCHITECTURE                               │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                    SPECIFY CLI (Python)                          │    │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐        │    │
│  │  │   init   │  │  check   │  │  help    │  │  update  │        │    │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘        │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                           │
│                              ▼                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                 SLASH COMMAND LAYER                              │    │
│  │  ┌────────────┐  ┌────────────┐  ┌────────────┐                 │    │
│  │  │constitution│  │  specify   │  │    plan    │                 │    │
│  │  └────────────┘  └────────────┘  └────────────┘                 │    │
│  │  ┌────────────┐  ┌────────────┐  ┌────────────┐                 │    │
│  │  │   tasks    │  │ implement  │  │  analyze   │                 │    │
│  │  └────────────┘  └────────────┘  └────────────┘                 │    │
│  │  ┌────────────┐  ┌────────────┐  ┌────────────┐                 │    │
│  │  │  clarify   │  │ checklist  │  │taskstoissues│                │    │
│  │  └────────────┘  └────────────┘  └────────────┘                 │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                           │
│                              ▼                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                    TEMPLATE SYSTEM                               │    │
│  │  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐  │    │
│  │  │ spec-template   │  │ plan-template   │  │ tasks-template  │  │    │
│  │  └─────────────────┘  └─────────────────┘  └─────────────────┘  │    │
│  │  ┌─────────────────┐  ┌─────────────────┐                       │    │
│  │  │checklist-template│  │agent-file-template│                     │    │
│  │  └─────────────────┘  └─────────────────┘                       │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                           │
│                              ▼                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │              PROJECT ARTIFACT STRUCTURE                          │    │
│  │                                                                   │    │
│  │    project/                                                       │    │
│  │    ├── memory/                                                    │    │
│  │    │   └── constitution.md        # Governance principles         │    │
│  │    ├── specs/                                                     │    │
│  │    │   └── {N}-{feature}/                                        │    │
│  │    │       ├── spec.md            # Feature specification         │    │
│  │    │       ├── plan.md            # Technical plan                │    │
│  │    │       ├── tasks.md           # Task breakdown                │    │
│  │    │       └── checklists/        # Validation checklists         │    │
│  │    └── .{agent}/                                                  │    │
│  │        └── commands/              # Agent-specific commands       │    │
│  │            └── speckit.*.md                                       │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

**Architecture Pattern**: Template-Driven Specification Pipeline

The architecture follows a layered approach where the CLI provides project initialization and health checks, slash commands orchestrate the specification workflow, templates enforce structure and consistency, and the resulting artifacts form a coherent project knowledge base.

---

## 3. Core Components

### 3.1 Specify CLI

The `specify` command-line tool serves as the entry point for Spec-Kit projects:

```bash
# Installation via uv (recommended)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Initialize a new project
specify init my-project --ai claude

# Check project health
specify check
```

**Key Commands**:
- `init <project-name>`: Bootstrap a new spec-driven project
- `check`: Verify tool installation and project structure
- `--ai <agent>`: Specify AI assistant (claude, gemini, copilot, cursor-agent, etc.)

### 3.2 Slash Command System

Nine slash commands orchestrate the spec-driven workflow:

| Command | Purpose | Output |
|---------|---------|--------|
| `/speckit.constitution` | Establish governance principles | `memory/constitution.md` |
| `/speckit.specify` | Create feature specification | `specs/{N}-{name}/spec.md` |
| `/speckit.plan` | Generate technical plan | `specs/{N}-{name}/plan.md` |
| `/speckit.tasks` | Break down into tasks | `specs/{N}-{name}/tasks.md` |
| `/speckit.implement` | Execute implementation | Code changes |
| `/speckit.analyze` | Validate specification | Analysis report |
| `/speckit.clarify` | Resolve ambiguities | Updated spec |
| `/speckit.checklist` | Generate validation checklist | Checklist file |
| `/speckit.taskstoissues` | Create GitHub issues | Issue links |

### 3.3 Constitution System

The constitution serves as the project's governance document:

```markdown
# Project Constitution v1.0.0

## Article I: Library-First Architecture
All components MUST be designed as libraries before CLI wrappers.

## Article II: CLI Mandate
User-facing functionality MUST have CLI interface.

## Article III: Test-First Imperative
No code ships without tests. TDD is non-negotiable.

## Article IV: Technology Stack
- Language: TypeScript 5.x
- Runtime: Node.js 20+
- Testing: Vitest
```

### 3.4 Template System

Templates enforce consistent artifact structure:

```markdown
<!-- spec-template.md -->
# Feature: [FEATURE_NAME]

## What
[Clear description of the feature]

## Why
[Business value and user benefit]

## User Stories
[Acceptance criteria in Given/When/Then format]

## Assumptions
[Explicit assumptions made]

## Out of Scope
[What this feature does NOT include]
```

### 3.5 Multi-Agent Support

Spec-Kit supports 16+ AI coding assistants through agent-specific adapters:

```python
AGENT_CONFIG = {
    "claude": {"folder": ".claude/commands/", "format": "md"},
    "gemini": {"folder": ".gemini/commands/", "format": "toml"},
    "copilot": {"folder": ".github/agents/", "format": "md"},
    "cursor-agent": {"folder": ".cursor/commands/", "format": "md"},
    "qwen": {"folder": ".qwen/commands/", "format": "toml"},
    # ... 11 more agents
}
```

---

## 4. Design Patterns

### 4.1 Constitutional Governance Pattern

Borrowed from political governance, this pattern establishes immutable principles that guide all development decisions:

```markdown
## Governance
- Amendment requires explicit version bump
- MAJOR: Backward-incompatible principle changes
- MINOR: New principles or expansions
- PATCH: Clarifications and typo fixes
```

**Benefits**: Prevents scope creep, ensures consistency, documents decisions.

### 4.2 Specification-as-Code Pattern

Specifications are treated as executable artifacts, not documentation:

```bash
# Specification drives implementation
/speckit.specify Build user authentication with OAuth2
# Generates structured spec that AI can execute deterministically
```

### 4.3 Template-Driven Constraint Pattern

Templates productively constrain AI output by providing structure:

```markdown
# Template forces specific sections
## What: [REQUIRED - one paragraph]
## Why: [REQUIRED - business value]
## Success Criteria: [REQUIRED - measurable outcomes]
```

### 4.4 Progressive Refinement Pattern

Specifications evolve through clarification cycles:

```
specify → clarify → plan → clarify → tasks → implement
         ↑___________|      ↑_________|
         Feedback loops for refinement
```

### 4.5 Agent Abstraction Pattern

Commands work identically across AI assistants:

```bash
# Same command, different agents
/speckit.specify (works in Claude, Copilot, Cursor, etc.)

# Agent-specific files generated during init
.claude/commands/speckit.specify.md
.cursor/commands/speckit.specify.md
```

---

## 5. Strengths

1. **Universal AI Compatibility**: Works with 16+ AI coding assistants through standardized command interface, preventing vendor lock-in.

2. **Governance-First Design**: Constitutional system ensures project principles are explicit, versioned, and enforced throughout development.

3. **Structured Output Guarantee**: Template-driven approach ensures AI outputs are consistent and complete, reducing variability.

4. **Specification Traceability**: Clear lineage from requirement to implementation through spec → plan → tasks → code chain.

5. **Quality Validation Built-In**: Checklist generation and analyze commands catch issues before implementation.

6. **Low Barrier to Entry**: Simple CLI installation (`uv tool install`) and intuitive slash command interface.

7. **GitHub Native Integration**: `/speckit.taskstoissues` creates GitHub issues directly, integrating with existing workflows.

8. **Technology Agnostic Specifications**: Specs focus on WHAT and WHY, not HOW, enabling technology changes without spec rewrites.

9. **Community Momentum**: 52k+ stars in 3.5 months indicates strong adoption and validation.

10. **Official GitHub Backing**: Maintained by GitHub ensures long-term support and integration with GitHub ecosystem.

---

## 6. Limitations

1. **Upfront Investment Required**: Creating comprehensive specifications takes time; not suitable for quick experiments or prototypes.

2. **Specification Maintenance Burden**: Specs must be kept in sync with implementation; drift causes confusion.

3. **Template Rigidity**: Predefined templates may not fit all project types; customization requires template modification.

4. **Python 3.11+ Requirement**: Limits adoption in environments with older Python versions.

5. **Learning Curve for Constitution**: Teams unfamiliar with governance patterns may struggle to write effective constitutions.

6. **Limited Brownfield Support**: While supported, retrofitting existing projects with specifications is challenging.

7. **AI Dependency**: Workflow assumes AI assistant availability; manual spec creation is possible but tedious.

8. **No Built-in Versioning**: Specifications don't have built-in version control beyond Git commits.

9. **Single-Project Focus**: No native support for mono-repo or multi-project specification management.

10. **Limited IDE Integration**: Primarily CLI-based; no dedicated IDE plugins for spec visualization or editing.

---

## 7. Production Readiness

### 7.1 SOLID Score: 4.3/5.0

**Single Responsibility Principle (SRP): 4.5/5.0**
Each slash command has a single, well-defined purpose. The `specify` command creates specs, `plan` creates plans, `tasks` creates tasks. No command tries to do multiple things. The CLI is cleanly separated from the command templates, and templates are separated from the artifact structure. Minor deduction for some template files containing both structure and guidance content.

**Open/Closed Principle (OCP): 4.5/5.0**
The agent configuration system exemplifies OCP - adding new AI agents requires only adding entries to `AGENT_CONFIG` dictionary without modifying existing code. Template system is extensible through new templates. Command system allows new commands through new template files. The architecture is highly extensible without modification.

**Liskov Substitution Principle (LSP): 4.0/5.0**
All AI agents can be substituted through the `--ai` flag without changing behavior. Commands work identically across agents. However, some agents have different capabilities (CLI vs IDE-based) which creates subtle behavioral differences. Template format differences (Markdown vs TOML) require different handling.

**Interface Segregation Principle (ISP): 4.5/5.0**
Commands expose minimal interfaces - each slash command takes only the arguments it needs. The CLI has separate subcommands for different operations. Users interact only with the commands relevant to their current workflow stage. No forced interaction with unused functionality.

**Dependency Inversion Principle (DIP): 4.0/5.0**
The system depends on abstractions (templates, command structure) rather than concrete implementations. However, the tight coupling to Git for branch management and filesystem for artifact storage creates some concrete dependencies. The Python CLI has direct dependencies on specific libraries.

### 7.2 Production Score: 78/100

| Dimension | Score | Justification |
|-----------|-------|---------------|
| **Reliability** | 80/100 | Mature codebase with 22 releases, active maintenance, comprehensive error handling in CLI. Template-based approach reduces runtime failures. Git-based artifact storage provides durability. |
| **Observability** | 70/100 | Clear artifact structure enables inspection. `specify check` provides health validation. No built-in metrics or telemetry. Specification audit trail through Git history. Limited real-time monitoring. |
| **Security** | 82/100 | No credential storage in specifications. Token handling delegated to AI assistants. MIT license with clear terms. No network calls except Git operations. Constitution can encode security principles. |
| **Performance** | 85/100 | CLI operations are fast (< 1s). Template rendering is instant. No background processes. Artifact size scales linearly with project complexity. No performance bottlenecks identified. |
| **Maintainability** | 73/100 | Clean Python codebase with type hints. Comprehensive AGENTS.md documentation. Template system is straightforward. Single source of truth for agent config. Some complexity in multi-agent support. |

---

## 8. Comparative Analysis

### 8.1 vs BMad Method

| Aspect | GitHub Spec-Kit | BMad Method |
|--------|-----------------|-------------|
| **Approach** | Spec-driven, constitutional | Agile-based, 19-agent orchestration |
| **AI Dependency** | Works with 16+ agents | Primarily Claude-focused |
| **Complexity** | Low (9 commands) | High (19 specialized agents) |
| **Governance** | Constitutional articles | Workflow rules |
| **Best For** | Specification-heavy projects | Complex multi-agent workflows |

**Verdict**: Spec-Kit for specification clarity; BMad for complex orchestration.

### 8.2 vs SuperClaude

| Aspect | GitHub Spec-Kit | SuperClaude |
|--------|-----------------|-------------|
| **Focus** | Specification creation | Cognitive personas |
| **Structure** | Templates + commands | CLAUDE.md rules |
| **Multi-Agent** | 16+ agents | Claude-only |
| **Artifacts** | specs/, memory/ | Session-based |
| **Installation** | CLI tool | File copy |

**Verdict**: Spec-Kit for multi-agent teams; SuperClaude for Claude-exclusive workflows.

### 8.3 vs Clavix

| Aspect | GitHub Spec-Kit | Clavix |
|--------|-----------------|--------|
| **Primary Focus** | Specification management | Prompt optimization |
| **Workflow** | Constitution → Spec → Plan → Tasks | Improve → PRD → Plan |
| **Output** | Structured artifacts | Optimized prompts |
| **Maintainer** | GitHub (official) | ClavixDev (community) |

**Verdict**: Spec-Kit for full lifecycle; Clavix for prompt refinement.

### 8.4 vs Traditional Waterfall

| Aspect | GitHub Spec-Kit | Traditional Waterfall |
|--------|-----------------|----------------------|
| **Specifications** | Living, executable | Static documents |
| **Iteration** | Built-in clarification loops | Phase-gated |
| **AI Integration** | Native | None |
| **Traceability** | Automatic through artifacts | Manual tracking |

**Verdict**: Spec-Kit brings waterfall rigor with agile flexibility.

---

## 9. Integration Patterns

### 9.1 CI/CD Integration

```yaml
# .github/workflows/spec-validation.yml
name: Validate Specifications
on: [pull_request]

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Install specify
        run: uv tool install specify-cli --from git+https://github.com/github/spec-kit.git
      - name: Check spec health
        run: specify check
      - name: Validate no TODO markers
        run: |
          if grep -r "TODO\|NEEDS CLARIFICATION" specs/; then
            echo "Unresolved items found in specifications"
            exit 1
          fi
```

### 9.2 GitHub Issues Integration

```bash
# Convert tasks to GitHub issues
/speckit.taskstoissues

# Creates issues with:
# - Title from task name
# - Body from task description
# - Labels based on task category
# - Linked to specification
```

### 9.3 Documentation Generation

```bash
# Specification artifacts serve as documentation
specs/
├── 1-user-auth/
│   ├── spec.md      # Feature documentation
│   ├── plan.md      # Technical design doc
│   └── tasks.md     # Implementation guide
```

### 9.4 Code Review Integration

```markdown
<!-- PR template -->
## Specification Reference
- Spec: specs/{N}-{feature}/spec.md
- Plan: specs/{N}-{feature}/plan.md

## Constitutional Compliance
- [ ] Follows Article I: Library-First
- [ ] Follows Article III: Test-First
```

---

## 10. Best Practices

### 10.1 Constitution Design

```markdown
# Good constitution principles
## Article I: Single Source of Truth
Specifications MUST be the authoritative source for feature requirements.

# Bad constitution principles
## Article I: Be Good
Code should be good quality. (Too vague, not testable)
```

### 10.2 Specification Writing

```markdown
# Good specification
## What
Users can authenticate using their Google account via OAuth2.

## Success Criteria
- Login completes in under 3 seconds
- 99.9% authentication success rate
- Session persists for 30 days

# Bad specification
## What
Add Google login with OAuth2 using passport.js library.
(Contains implementation details)
```

### 10.3 Workflow Discipline

```bash
# Correct workflow
/speckit.constitution   # First: establish principles
/speckit.specify        # Second: create spec
/speckit.clarify        # Third: resolve ambiguities
/speckit.plan           # Fourth: technical design
/speckit.tasks          # Fifth: break down work
/speckit.implement      # Sixth: build it

# Anti-pattern: jumping to implementation
/speckit.implement      # Without spec = "vibe coding"
```

### 10.4 Multi-Agent Teams

```bash
# Team using different AI assistants
specify init project --ai claude    # Developer A
specify init project --ai cursor    # Developer B

# Both work on same specs/ artifacts
# Commands are agent-specific but artifacts are universal
```

---

## 11. Configuration Reference

### 11.1 Project Initialization

```bash
specify init <project-name> [OPTIONS]

Options:
  --ai <agent>     AI assistant: claude, gemini, copilot, cursor-agent,
                   qwen, opencode, codex, windsurf, kilocode, auggie,
                   codebuddy, q, amp, shai, bob
  --help           Show help message
```

### 11.2 Directory Structure

```
project/
├── memory/
│   └── constitution.md      # Project principles
├── specs/
│   └── {N}-{feature}/
│       ├── spec.md          # Feature specification
│       ├── plan.md          # Technical plan
│       ├── tasks.md         # Task breakdown
│       └── checklists/
│           └── requirements.md
├── templates/
│   └── commands/            # Slash command templates
└── .{agent}/
    └── commands/
        └── speckit.*.md     # Agent-specific commands
```

### 11.3 Template Customization

```markdown
<!-- Custom spec-template.md -->
# Feature: [FEATURE_NAME]

## Business Context
[Company-specific section]

## Regulatory Requirements
[Compliance section for regulated industries]

## What
[Standard section]
```

### 11.4 Agent Configuration

```python
# Custom agent in AGENT_CONFIG
"custom-agent": {
    "name": "Custom Agent",
    "folder": ".customagent/commands/",
    "install_url": "https://custom.agent/install",
    "requires_cli": True,
}
```

---

## 12. Recommendations

### 12.1 For Adoption

1. **Start with Constitution**: Spend time defining project principles before writing specs.
2. **Pilot on New Feature**: Try spec-driven approach on one new feature first.
3. **Train on Templates**: Ensure team understands template structure and purpose.
4. **Integrate Gradually**: Add spec validation to CI/CD incrementally.

### 12.2 For Use Cases

- **Best Fit**: Enterprise software, regulated industries, distributed teams
- **Good Fit**: Complex features, cross-team projects, documentation-heavy
- **Poor Fit**: Quick prototypes, solo experiments, trivial changes

### 12.3 For Enhancement

1. **Custom Templates**: Create industry-specific template variants
2. **Constitution Library**: Build reusable constitution patterns
3. **Metrics Dashboard**: Track specification quality over time
4. **IDE Plugin**: Develop VS Code extension for spec editing

### 12.4 For Production

1. **Spec Review Process**: Establish specification review similar to code review
2. **Constitution Governance**: Define amendment process and approval chain
3. **Artifact Archival**: Plan for completed specification lifecycle
4. **Training Program**: Onboard team members on spec-driven methodology

---

## X. Workflow Definition

### X.1 Standard Spec-Driven Workflow

```
PHASE 1: GOVERNANCE
├── Input: Project vision and constraints
├── Command: /speckit.constitution
├── Output: memory/constitution.md
└── Validation: All principles are testable and versioned

PHASE 2: SPECIFICATION
├── Input: Feature description (natural language)
├── Command: /speckit.specify <description>
├── Process:
│   ├── Parse feature description
│   ├── Generate branch name (N-feature-name)
│   ├── Create spec.md from template
│   └── Run quality validation
├── Output: specs/{N}-{name}/spec.md
└── Validation: Max 3 [NEEDS CLARIFICATION] markers

PHASE 3: CLARIFICATION (if needed)
├── Input: Spec with unresolved items
├── Command: /speckit.clarify
├── Process:
│   ├── Extract clarification markers
│   ├── Present options to user
│   └── Update spec with choices
├── Output: Updated spec.md
└── Validation: No clarification markers remain

PHASE 4: PLANNING
├── Input: Validated specification
├── Command: /speckit.plan
├── Process:
│   ├── Analyze spec requirements
│   ├── Define technical approach
│   ├── Identify dependencies
│   └── Create architecture decisions
├── Output: specs/{N}-{name}/plan.md
└── Validation: Plan aligns with constitution

PHASE 5: TASK BREAKDOWN
├── Input: Technical plan
├── Command: /speckit.tasks
├── Process:
│   ├── Decompose plan into tasks
│   ├── Assign task numbers (T1.1, T1.2, etc.)
│   ├── Define dependencies
│   └── Estimate complexity
├── Output: specs/{N}-{name}/tasks.md
└── Validation: All tasks are actionable

PHASE 6: IMPLEMENTATION
├── Input: Task list
├── Command: /speckit.implement
├── Process:
│   ├── Execute tasks in order
│   ├── Respect dependencies
│   └── Follow constitution principles
├── Output: Code changes
└── Validation: Implementation matches spec
```

### X.2 Workflow Variants

**Quick Path** (Simple Features):
```
/speckit.specify → /speckit.plan → /speckit.implement
```

**Full Path** (Complex Features):
```
/speckit.constitution → /speckit.specify → /speckit.clarify →
/speckit.plan → /speckit.tasks → /speckit.checklist →
/speckit.implement → /speckit.analyze
```

**Brownfield Path** (Existing Projects):
```
/speckit.analyze (understand existing) → /speckit.constitution →
/speckit.specify (new features only)
```

---

## Y. Prompt Engineering

### Y.1 Specification Prompt Patterns

**Constitution Priming**:
```bash
/speckit.constitution Create principles focused on:
- Code quality (testing, reviews)
- User experience consistency
- Performance requirements
- Security standards
```

**Feature Description Pattern**:
```bash
/speckit.specify Build [FEATURE] that allows [USER] to [ACTION]
so that [BENEFIT]. Include [CONSTRAINTS].

# Example
/speckit.specify Build a photo album feature that allows users to
organize photos by date with drag-and-drop reordering so that
they can easily manage their photo collections. Include support
for albums but not nested albums.
```

### Y.2 Template-Driven Constraints

Templates constrain AI output through required sections:

```markdown
# spec-template.md forces these sections:
## What         # Prevents vague descriptions
## Why          # Forces business justification
## User Stories # Requires testable scenarios
## Assumptions  # Makes implicit explicit
## Out of Scope # Prevents scope creep
```

### Y.3 Clarification Prompt Pattern

```markdown
## Question [N]: [Topic]

**Context**: [Quote relevant spec section]

**What we need to know**: [Specific question]

**Suggested Answers**:
| Option | Answer | Implications |
|--------|--------|--------------|
| A      | [First option] | [Impact] |
| B      | [Second option] | [Impact] |
| C      | [Third option] | [Impact] |
```

### Y.4 Few-Shot Examples in Templates

Templates include examples to guide AI:

```markdown
**Good examples** (Success Criteria):
- "Users can complete checkout in under 3 minutes"
- "System supports 10,000 concurrent users"

**Bad examples** (Implementation-focused):
- "API response time is under 200ms"
- "Database can handle 1000 TPS"
```

---

## Z. Guardrails and Quality

### Z.1 Specification Quality Checklist

```markdown
## Content Quality
- [ ] No implementation details (languages, frameworks, APIs)
- [ ] Focused on user value and business needs
- [ ] Written for non-technical stakeholders
- [ ] All mandatory sections completed

## Requirement Completeness
- [ ] No [NEEDS CLARIFICATION] markers remain
- [ ] Requirements are testable and unambiguous
- [ ] Success criteria are measurable
- [ ] Success criteria are technology-agnostic

## Feature Readiness
- [ ] All functional requirements have acceptance criteria
- [ ] User scenarios cover primary flows
- [ ] Edge cases are identified
- [ ] Scope is clearly bounded
```

### Z.2 Constitution Validation Rules

```markdown
# Valid principle
## Article I: Test-First Imperative
All code MUST have tests before merge. No exceptions.
Rationale: Prevents regression and ensures quality.

# Invalid principle (too vague)
## Article I: Quality
Code should be good. (Not testable, no enforcement)
```

### Z.3 Plan Validation

```markdown
## Constitutional Compliance Check
- [ ] Plan follows Article I: Library-First
- [ ] Plan follows Article II: CLI Mandate
- [ ] Plan follows Article III: Test-First
- [ ] No constitutional violations identified
```

### Z.4 Task Validation

```markdown
## Task Quality Criteria
- [ ] Each task is independently completable
- [ ] Dependencies are explicitly declared
- [ ] Acceptance criteria are clear
- [ ] Complexity estimate provided
```

### Z.5 Implementation Guardrails

```markdown
## Pre-Implementation Checklist
- [ ] Specification is approved
- [ ] Plan is reviewed
- [ ] Tasks are assigned
- [ ] Constitution is loaded in context

## Post-Implementation Checklist
- [ ] All tasks completed
- [ ] Tests pass
- [ ] No constitution violations
- [ ] Spec requirements met
```

---

## Sources and References

1. **Primary Repository**: https://github.com/github/spec-kit
2. **Official Documentation**: https://github.github.io/spec-kit/
3. **GitHub Blog Announcement**: https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/
4. **Installation Guide**: https://github.com/github/spec-kit/blob/main/docs/installation.md
5. **AGENTS.md Reference**: https://github.com/github/spec-kit/blob/main/AGENTS.md
6. **Template Reference**: https://github.com/github/spec-kit/tree/main/templates
7. **Changelog**: https://github.com/github/spec-kit/blob/main/CHANGELOG.md
8. **Microsoft Developer Blog**: https://developer.microsoft.com/blog/spec-driven-development-spec-kit

---

*Analysis generated via rcr-research:framework-analyzer skill with confirmed invocation*


---

<footer class="generation-meta">
<small>
Generated: 2025-12-01 22:56 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/github-speckit">Source Data</a>
</small>
</footer>