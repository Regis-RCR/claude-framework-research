---
title: Clavix
layout: default
parent: Frameworks
---

# Clavix

<div class="framework-meta">
<strong>Version:</strong> 5.7.1 |
<strong>Repository:</strong> <a href="https://github.com/ClavixDev/Clavix">GitHub</a> |
<strong>License:</strong> Apache-2.0
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: cli, prompt-based</span>
<span class="badge badge-exec">exec: single-agent</span>
<span class="badge badge-function">function: dev-methodology</span>
<span class="badge badge-ecosystem">ecosystem: nodejs</span>
<span class="badge badge-scope">scope: session-level</span>
<span class="badge badge-integration">integration: drop-in</span>
<span class="badge badge-user">user: solo-dev, team</span>
<span class="badge badge-complexity">complexity: low</span>
<span class="badge badge-maturity">maturity: stable</span>
<span class="badge badge-community">community: growing</span>
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
<td>4.1/5.0 ⭐⭐⭐⭐☆</td>
<td><strong>Overall</strong></td>
<td>72/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>4.5/5.0</td>
<td>Reliability</td>
<td>75</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>4.0/5.0</td>
<td>Observability</td>
<td>65</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>4.0/5.0</td>
<td>Security</td>
<td>78</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>4.0/5.0</td>
<td>Performance</td>
<td>80</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>4.0/5.0</td>
<td>Maintainability</td>
<td>70</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Agentic-first instruction injection architecture</li>
<li>Templates-as-product philosophy (zero TypeScript during execution)</li>
<li>Multi-tool support (20+ AI coding assistants)</li>
<li>Mode enforcement (Planning vs Implementation)</li>
<li>Component-based template assembly with INCLUDE markers</li>
<li>Quality dimension analysis (6 dimensions)</li>
</ul>

## Best For

<ul class="compact-list">
<li>Prompt optimization and refinement</li>
<li>PRD generation through Socratic questioning</li>
<li>Task breakdown and planning</li>
<li>Conversational requirements gathering</li>
<li>Implementation verification</li>
</ul>

## Limitations

<ul class="compact-list">
<li>No runtime validation guarantees</li>
<li>Depends on AI agent compliance</li>
<li>Node.js 18+ requirement</li>
<li>Smaller community than GitHub alternatives</li>
<li>No semantic understanding of outputs</li>
</ul>

---

## Full Analysis

# Clavix - Framework Analysis

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

Clavix is an agentic-first prompt workflow system that uses markdown templates to teach AI coding agents structured approaches to prompt optimization, PRD generation, and implementation management. Unlike traditional tools that execute code at runtime, Clavix's slash commands are pure markdown instructions that AI agents read and follow using their native capabilities.

**Key Value Proposition**: Transform ad-hoc AI interactions into structured, repeatable workflows by injecting guidance templates that any of 20+ AI coding assistants can follow consistently, without requiring runtime code execution.

The framework operates on a revolutionary principle: "Templates ARE the product." When a user invokes `/clavix:improve`, no TypeScript executes - the AI agent simply reads the template file and follows its instructions using built-in tools like Write, Edit, and Bash. This architecture enables:

1. **Zero-execution overhead** - Only filesystem operations during setup
2. **Universal compatibility** - Works with any AI that can read markdown
3. **Transparent workflows** - All logic visible in human-readable templates
4. **Instant updates** - Change workflow by editing markdown, no recompilation

**Core Innovation**: The "agentic-first instruction injection" pattern treats AI agents as the runtime environment, injecting structured workflows through template files rather than orchestrating agents through APIs. This inverts the typical control flow where code calls AI; instead, AI reads and executes code-as-documentation.

---

## 2. Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────────┐
│                      CLAVIX ARCHITECTURE                                 │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                    CLI LAYER (Setup Only)                        │    │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐        │    │
│  │  │   init   │  │  update  │  │ diagnose │  │ version  │        │    │
│  │  └──────────┘  └──────────┘  └──────────┘  └──────────┘        │    │
│  │         Only these execute TypeScript at runtime                │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                           │
│                              ▼                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                 TEMPLATE INJECTION LAYER                         │    │
│  │                                                                   │    │
│  │    User runs: clavix init                                        │    │
│  │         ↓                                                         │    │
│  │    Detection: Which AI tools installed?                          │    │
│  │         ↓                                                         │    │
│  │    Generation: Create agent-specific files                       │    │
│  │         ↓                                                         │    │
│  │    .claude/commands/clavix/    .cursor/commands/                 │    │
│  │    .gemini/commands/clavix/    AGENTS.md                         │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                           │
│                              ▼                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                 SLASH COMMAND LAYER (9 Commands)                 │    │
│  │                                                                   │    │
│  │    PLANNING MODE              IMPLEMENTATION MODE                │    │
│  │  ┌────────────┐             ┌────────────┐                       │    │
│  │  │  improve   │             │ implement  │                       │    │
│  │  │    prd     │             └────────────┘                       │    │
│  │  │   plan     │                                                  │    │
│  │  │   start    │             VERIFICATION MODE                    │    │
│  │  │ summarize  │             ┌────────────┐                       │    │
│  │  │  refine    │             │   verify   │                       │    │
│  │  └────────────┘             │  archive   │                       │    │
│  │                              └────────────┘                       │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                           │
│                              ▼                                           │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                 OUTPUT STRUCTURE                                  │    │
│  │                                                                   │    │
│  │    .clavix/                                                       │    │
│  │    ├── config.json           # Configuration                     │    │
│  │    ├── INSTRUCTIONS.md       # Generated guide                   │    │
│  │    └── outputs/                                                   │    │
│  │        ├── prompts/          # From /clavix:improve              │    │
│  │        ├── {project}/        # From /clavix:prd                  │    │
│  │        │   ├── full-prd.md                                        │    │
│  │        │   ├── quick-prd.md                                       │    │
│  │        │   └── tasks.md                                           │    │
│  │        └── archive/          # From /clavix:archive              │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

**Architecture Pattern**: Agentic-First Instruction Injection

The architecture fundamentally differs from orchestration frameworks. Instead of code controlling AI agents, Clavix injects instructions that AI agents autonomously follow. This creates a declarative workflow system where templates define behavior and agents provide execution.

---

## 3. Core Components

### 3.1 CLI Commands (4 total)

The CLI exists solely for environment setup:

```bash
# Initialize Clavix in a project
clavix init

# Update templates after package upgrade
clavix update

# Check installation health
clavix diagnose

# Show version
clavix version
```

**Critical Point**: These are the ONLY commands that execute TypeScript. All slash commands are pure markdown templates.

### 3.2 Slash Commands (9 total)

Markdown templates that AI agents read and execute:

| Command | Stage | Purpose |
|---------|-------|---------|
| `/clavix:improve` | Optimize | Smart prompt optimization with auto-depth |
| `/clavix:prd` | Document | Guided PRD generation via Socratic questions |
| `/clavix:plan` | Plan | Task breakdown from PRD artifacts |
| `/clavix:implement` | Implement | Execute tasks or prompts |
| `/clavix:start` | Explore | Conversational requirements gathering |
| `/clavix:summarize` | Document | Extract requirements from conversation |
| `/clavix:refine` | Refine | Update existing PRD or prompt |
| `/clavix:verify` | Verify | Check implementation against checklist |
| `/clavix:archive` | Manage | Archive completed projects |

### 3.3 Template Assembly System

Templates use component markers for reusability:

```markdown
<!-- improve.md -->
# Improve Command

{{INCLUDE:_components/AGENT_MANUAL.md}}

## Instructions
1. Analyze the prompt
2. Apply optimization patterns
{{INCLUDE:_components/quality-dimensions.md}}
3. Save result
```

**Component Library**:
- `AGENT_MANUAL.md` - Universal agent protocols
- `cli-reference.md` - Command documentation
- `state-awareness.md` - Mode tracking
- `quality-dimensions.md` - Analysis criteria

### 3.4 Multi-Tool Adapters

Each AI tool has specific requirements:

```typescript
// Adapter configuration
const adapters = {
  claude: {
    path: '.claude/commands/clavix/',
    format: 'md',
    separator: ':'
  },
  cursor: {
    path: '.cursor/commands/',
    format: 'md',
    separator: '-'
  },
  gemini: {
    path: '.gemini/commands/clavix/',
    format: 'md',
    separator: ':'
  }
  // ... 17 more adapters
};
```

### 3.5 Mode Enforcement System

Every workflow declares its mode:

```markdown
**CLAVIX MODE: Improve**
Mode: planning
Purpose: Optimizing user prompt
Implementation: BLOCKED
```

Modes prevent premature code generation by making the current phase explicit.

---

## 4. Design Patterns

### 4.1 Agentic-First Pattern

Agents as runtime, templates as programs:

```
Traditional: Code → API Call → AI Response → Code processes
Clavix:      Template → Agent reads → Agent executes → Output files
```

**Benefits**: No API management, no rate limiting, no token counting in application code.

### 4.2 Instruction Injection Pattern

Templates injected into agent-specific locations:

```bash
# Agent reads from its designated location
.claude/commands/clavix/improve.md    # Claude Code
.cursor/commands/clavix-improve.md    # Cursor
.gemini/commands/clavix/improve.md    # Gemini
```

### 4.3 Mode-First Development Pattern

All workflows start in planning mode:

```markdown
## Mode Boundaries
- Asking clarifying questions ✓
- Analyzing requirements ✓
- Generating documentation ✓
- Writing code ✗ BLOCKED
```

Implementation only occurs after explicit mode transition.

### 4.4 Socratic Questioning Pattern

PRD generation through guided questions:

```markdown
## Question Flow
1. What problem are you solving?
2. Who is the target user?
3. What does success look like?
4. What constraints exist?
→ Generate PRD from answers
```

### 4.5 Quality Dimension Analysis Pattern

Prompts evaluated across 6 dimensions:

```markdown
## Quality Dimensions
1. Clarity - Is the intent unambiguous?
2. Efficiency - Is it concise?
3. Structure - Is it well-organized?
4. Completeness - Are all requirements stated?
5. Actionability - Can it be executed immediately?
6. Specificity - Are details concrete?
```

---

## 5. Strengths

1. **Zero Runtime Execution**: Slash commands execute no code, eliminating an entire class of bugs and security concerns.

2. **Universal Compatibility**: Works with 20+ AI tools through adapter system, preventing vendor lock-in.

3. **Transparent Workflows**: All logic visible in markdown templates - no hidden behavior, fully auditable.

4. **Instant Updates**: Modify workflows by editing markdown; no build, no deploy, no restart.

5. **Mode Enforcement**: Prevents premature implementation by making planning phase explicit and blocking code generation.

6. **Structured Output**: Consistent artifact structure (PRDs, tasks, prompts) across all projects and teams.

7. **Progressive Disclosure**: Simple quick path (`improve → implement`) or full workflow (`prd → plan → implement → verify → archive`).

8. **Diagnostic Tools**: `clavix diagnose` catches configuration issues early.

9. **Active Development**: Regular releases (v5.7.1), responsive maintainers, comprehensive documentation.

10. **Apache 2.0 License**: Permissive licensing suitable for commercial use.

---

## 6. Limitations

1. **No Validation Guarantees**: Cannot force AI agents to follow templates correctly; compliance depends on agent behavior.

2. **No Semantic Understanding**: Templates guide structure but cannot evaluate output quality or correctness.

3. **Agent-Dependent Quality**: Output quality varies significantly between AI assistants.

4. **No Persistence Layer**: No database, no session management - all state in filesystem.

5. **Limited Error Recovery**: If an agent diverges from template, no automatic correction mechanism.

6. **Node.js Requirement**: Requires Node.js 18+ for CLI, limiting some environments.

7. **Smaller Community**: 147 stars vs. GitHub Spec-Kit's 52k - less ecosystem support.

8. **No Multi-Project Coordination**: Designed for single project scope, no mono-repo support.

9. **Documentation Injection Only**: Cannot modify agent behavior, only suggest through documentation.

10. **Template Complexity**: Advanced workflows require understanding template assembly system.

---

## 7. Production Readiness

### 7.1 SOLID Score: 4.1/5.0

**Single Responsibility Principle (SRP): 4.5/5.0**
Each slash command has exactly one purpose. The `improve` command optimizes prompts, `prd` generates PRDs, `plan` creates task breakdowns. CLI commands are similarly focused: `init` initializes, `diagnose` checks health. Template components are also single-purpose (`AGENT_MANUAL.md` for protocols, `quality-dimensions.md` for analysis criteria). Minor deduction for some templates handling multiple sub-workflows.

**Open/Closed Principle (OCP): 4.0/5.0**
Adding new AI tool support requires only adding an adapter entry, not modifying core logic. New slash commands can be added as new template files. However, modifying existing command behavior requires editing templates directly rather than extending them. The component system partially addresses this through `{{INCLUDE}}` markers.

**Liskov Substitution Principle (LSP): 4.0/5.0**
AI agents are substitutable - any agent that can read markdown can execute Clavix workflows. Different adapters produce equivalent command files. However, agent capability differences (Claude vs. Cursor vs. Gemini) create subtle behavioral variations that templates cannot fully abstract.

**Interface Segregation Principle (ISP): 4.0/5.0**
Commands expose minimal interfaces - users interact only with slash commands they need. The CLI has focused subcommands. However, the `implement` command handles multiple modes (task mode, prompt mode) which could be split into separate commands.

**Dependency Inversion Principle (DIP): 4.0/5.0**
The system depends on abstractions (adapters, templates) rather than concrete AI implementations. However, the tight coupling to filesystem structure and specific markdown formats creates concrete dependencies. Templates directly reference file paths rather than abstract locations.

### 7.2 Production Score: 72/100

| Dimension | Score | Justification |
|-----------|-------|---------------|
| **Reliability** | 75/100 | Mature codebase with 174 commits, 40 releases. File-based operations are inherently reliable. No network dependencies during workflow execution. Template failures are visible and debuggable. |
| **Observability** | 65/100 | `clavix diagnose` provides health checks. Output files create audit trail. No telemetry or metrics. Mode assertions make state visible. Limited real-time visibility into agent execution. |
| **Security** | 78/100 | No credential handling. No network calls during workflows. Apache 2.0 license. Templates are human-readable and auditable. Depends on agent's sandbox for code execution safety. |
| **Performance** | 80/100 | CLI operations are instant (< 100ms). No background processes. Templates load instantly. Scales linearly with project count. No performance bottlenecks in setup operations. |
| **Maintainability** | 70/100 | TypeScript codebase with tests. Clear documentation (architecture.md, commands.md). Template system adds complexity. Two maintainers limits bus factor. Component system aids reusability. |

---

## 8. Comparative Analysis

### 8.1 vs GitHub Spec-Kit

| Aspect | Clavix | GitHub Spec-Kit |
|--------|--------|-----------------|
| **Focus** | Prompt optimization + PRD | Specification management |
| **Governance** | Mode enforcement | Constitutional articles |
| **Commands** | 9 slash commands | 9 slash commands |
| **Maintainer** | ClavixDev (community) | GitHub (official) |
| **Stars** | 147 | 52,478 |
| **Best For** | Prompt refinement | Specification-first teams |

**Verdict**: Clavix for prompt-centric workflows; Spec-Kit for enterprise specifications.

### 8.2 vs SuperClaude

| Aspect | Clavix | SuperClaude |
|--------|--------|-------------|
| **Approach** | Template injection | Cognitive personas |
| **Runtime** | Zero execution | Zero execution |
| **Multi-Agent** | 20+ tools | Claude only |
| **Output** | Files in .clavix/ | Session-based |
| **Learning Curve** | Low (commands) | Medium (personas) |

**Verdict**: Clavix for multi-agent teams; SuperClaude for Claude-exclusive cognitive enhancement.

### 8.3 vs AB Method

| Aspect | Clavix | AB Method |
|--------|--------|-----------|
| **Paradigm** | Prompt optimization | Mission-based development |
| **Structure** | PRD → Tasks | Mission → Plan → Execute |
| **Verification** | /clavix:verify | Built-in checkpoints |
| **Installation** | npm package | File copy |

**Verdict**: Clavix for prompt-first; AB Method for mission-driven teams.

### 8.4 vs Traditional Prompt Engineering

| Aspect | Clavix | Manual Prompting |
|--------|--------|------------------|
| **Consistency** | Template-enforced | Varies by user |
| **Quality Analysis** | 6-dimension scoring | Ad-hoc evaluation |
| **Workflow** | Structured phases | Unstructured |
| **Artifacts** | Persistent files | Lost after session |

**Verdict**: Clavix for repeatable, documented prompt workflows.

---

## 9. Integration Patterns

### 9.1 Claude Code Integration

```bash
# Initialize for Claude Code
clavix init
# Select: Claude Code

# Result:
.claude/commands/clavix/
├── improve.md
├── prd.md
├── plan.md
├── implement.md
├── start.md
├── summarize.md
├── refine.md
├── verify.md
└── archive.md

# Usage in Claude Code
/clavix:improve "create a REST API for user management"
```

### 9.2 Cursor Integration

```bash
# Initialize for Cursor
clavix init
# Select: Cursor

# Result:
.cursor/commands/
├── clavix-improve.md
├── clavix-prd.md
└── ...

# Usage in Cursor (note hyphen)
/clavix-improve "add authentication"
```

### 9.3 Multi-Tool Setup

```bash
# Initialize for multiple tools
clavix init
# Select: Claude Code, Cursor, AGENTS.md

# Result: Files created in all selected locations
# All tools can work on same project
```

### 9.4 CI/CD Integration

```yaml
# .github/workflows/validate-prds.yml
name: Validate PRDs
on: [pull_request]

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Check PRD completeness
        run: |
          for prd in .clavix/outputs/*/full-prd.md; do
            if ! grep -q "## Success Criteria" "$prd"; then
              echo "Missing success criteria in $prd"
              exit 1
            fi
          done
```

---

## 10. Best Practices

### 10.1 Workflow Selection

```markdown
# Simple task → Quick path
/clavix:improve "add input validation"
/clavix:implement --latest

# Complex feature → Full workflow
/clavix:prd
/clavix:plan
/clavix:implement
/clavix:verify
/clavix:archive

# Uncertain requirements → Exploration
/clavix:start
[conversation]
/clavix:summarize
/clavix:plan
```

### 10.2 Prompt Quality

```markdown
# Good prompt input
/clavix:improve "Create a user authentication system with:
- Email/password login
- JWT tokens with 24h expiry
- Refresh token rotation
- Rate limiting (5 attempts/minute)
Target: Node.js/Express"

# Bad prompt input
/clavix:improve "add login"
```

### 10.3 PRD Refinement

```markdown
# After initial PRD generation
/clavix:refine
# Select PRD project
# Add: "Include OAuth2 social login"
# Modify: "Change session duration to 7 days"
# Then regenerate tasks
/clavix:plan
```

### 10.4 Verification Discipline

```markdown
# Always verify before considering complete
/clavix:implement
# [implementation complete]
/clavix:verify
# [review report]
# [fix any issues]
/clavix:verify  # Re-verify
# [all passed]
/clavix:archive
```

---

## 11. Configuration Reference

### 11.1 Project Configuration

```json
// .clavix/config.json
{
  "providers": ["claude", "cursor", "agents-md"],
  "outputDir": ".clavix/outputs",
  "defaultCommitStrategy": "per-phase"
}
```

### 11.2 Command Flags

```bash
# /clavix:prd flags
--quick           # Shorter question flow
--project <name>  # Name output directory
--skip-validation # Skip CLEAR analysis

# /clavix:plan flags
--source <type>   # auto|full|quick|mini|prompt
--max-tasks <n>   # Limit tasks per phase
--overwrite       # Replace existing tasks.md

# /clavix:implement flags
--tasks           # Force task mode
--latest          # Execute most recent prompt
--no-git          # Skip auto-commits
--commit-strategy # per-task|per-5-tasks|per-phase|none
```

### 11.3 Output Structure

```
.clavix/outputs/
├── prompts/
│   ├── 2024-01-15-user-auth-001.md
│   └── 2024-01-16-api-design-002.md
├── my-feature/
│   ├── full-prd.md
│   ├── quick-prd.md
│   ├── tasks.md
│   ├── mini-prd.md
│   ├── original-prompt.md
│   └── optimized-prompt.md
└── archive/
    └── completed-feature/
```

### 11.4 Supported Providers

| Provider | Path | Separator |
|----------|------|-----------|
| Claude Code | `.claude/commands/clavix/` | `:` |
| Cursor | `.cursor/commands/` | `-` |
| Windsurf | `.windsurf/commands/` | `-` |
| Gemini CLI | `.gemini/commands/clavix/` | `:` |
| Qwen CLI | `.qwen/commands/clavix/` | `:` |
| AGENTS.md | `AGENTS.md` | `:` |

---

## 12. Recommendations

### 12.1 For Adoption

1. **Start with Improve**: Begin using `/clavix:improve` on existing prompts before full workflow adoption.
2. **Single Tool First**: Initialize for one AI tool, master workflows, then add others.
3. **Document Outputs**: Review generated PRDs and tasks to understand template behavior.
4. **Iterative Refinement**: Use `/clavix:refine` liberally - PRDs improve through iteration.

### 12.2 For Use Cases

- **Best Fit**: Prompt optimization, PRD generation, structured planning
- **Good Fit**: Requirements documentation, task breakdown, verification
- **Poor Fit**: Real-time orchestration, complex agent coordination, runtime control

### 12.3 For Enhancement

1. **Custom Templates**: Create project-specific command variants in `.clavix/custom/`
2. **Team Standards**: Document quality dimensions relevant to your domain
3. **Archive Strategy**: Establish archival criteria and retention policies
4. **Integration Hooks**: Add CI checks for PRD completeness and task coverage

### 12.4 For Production

1. **Backup Outputs**: Include `.clavix/outputs/` in backup strategy
2. **Version Templates**: Track template changes alongside code changes
3. **Train Team**: Ensure all team members understand mode boundaries
4. **Monitor Quality**: Review generated artifacts for consistency

---

## X. Workflow Definition

### X.1 Complete Workflow Stages

```
STAGE 1: EXPLORATION (Optional)
├── Command: /clavix:start
├── Mode: Planning
├── Process:
│   ├── Enter conversational mode
│   ├── Ask clarifying questions
│   ├── Track requirements mentioned
│   └── Suggest summarize when ready
├── Output: Conversation history
└── Next: /clavix:summarize or /clavix:prd

STAGE 2: DOCUMENTATION
├── Commands: /clavix:prd OR /clavix:summarize
├── Mode: Planning
├── Process:
│   ├── Guided Socratic questioning (prd)
│   ├── OR extract from conversation (summarize)
│   ├── Generate comprehensive PRD
│   └── Create AI-optimized version
├── Output: full-prd.md, quick-prd.md (or mini-prd.md)
└── Next: /clavix:plan

STAGE 3: PLANNING
├── Command: /clavix:plan
├── Mode: Planning
├── Process:
│   ├── Read PRD artifacts
│   ├── Extract top-level features
│   ├── Group into phases
│   └── Generate task checklist
├── Output: tasks.md
└── Next: /clavix:implement

STAGE 4: IMPLEMENTATION
├── Command: /clavix:implement
├── Mode: Implementation (UNLOCKED)
├── Process:
│   ├── Load tasks or prompt
│   ├── Execute sequentially
│   ├── Track progress
│   └── Optional: auto-commit
├── Output: Code changes
└── Next: /clavix:verify

STAGE 5: VERIFICATION
├── Command: /clavix:verify
├── Mode: Verification
├── Process:
│   ├── Load requirements checklist
│   ├── Run automated tests
│   ├── Check against criteria
│   └── Generate report
├── Output: Verification report
└── Next: /clavix:archive or fix issues

STAGE 6: ARCHIVAL
├── Command: /clavix:archive
├── Mode: Management
├── Process:
│   ├── Check task completion
│   ├── Move to archive directory
│   └── Update project index
├── Output: Archived project
└── Next: New project
```

### X.2 Quick Path Workflow

```
/clavix:improve "prompt text"
     │
     ▼
Prompt optimization (auto-depth selection)
     │
     ▼
/clavix:implement --latest
     │
     ▼
Execute optimized prompt
     │
     ▼
/clavix:verify (optional)
```

### X.3 Iterative Refinement Loop

```
/clavix:prd → /clavix:plan
     ↑              │
     │              ▼
/clavix:refine ← Review tasks
     ↑              │
     │              ▼
   Issues ← /clavix:implement
     ↑              │
     │              ▼
   Report ← /clavix:verify
```

---

## Y. Prompt Engineering

### Y.1 Quality Dimension Analysis

Clavix evaluates prompts across 6 dimensions:

```markdown
## Clarity (Is intent unambiguous?)
- Single clear objective
- No conflicting requirements
- Explicit success criteria

## Efficiency (Is it concise?)
- No redundant information
- Focused scope
- Minimal words for maximum meaning

## Structure (Is it well-organized?)
- Logical section ordering
- Clear hierarchy
- Consistent formatting

## Completeness (Are all requirements stated?)
- All necessary context included
- Edge cases considered
- Dependencies identified

## Actionability (Can it be executed immediately?)
- No blocking questions
- Clear starting point
- Defined end state

## Specificity (Are details concrete?)
- Measurable criteria
- Named technologies (if relevant)
- Quantified requirements
```

### Y.2 Auto-Depth Selection

```markdown
## Depth Levels
- STANDARD: Good prompts needing minor refinement
- COMPREHENSIVE: Complex prompts needing major restructuring

## Selection Algorithm
Score = sum(dimension_scores) / 6
if Score >= 0.7: STANDARD
else: COMPREHENSIVE
```

### Y.3 Socratic PRD Generation

```markdown
## Question Categories
1. Problem Space
   - What problem are you solving?
   - Who experiences this problem?

2. Solution Space
   - What does success look like?
   - What's the minimum viable solution?

3. Constraints
   - What can't change?
   - What resources are limited?

4. Context
   - What exists today?
   - What integrations are needed?
```

### Y.4 Confidence Indicators

```markdown
## Confidence Levels in Summarize
- [HIGH] - Explicitly stated multiple times
- [MEDIUM] - Mentioned once or clearly inferred
- [LOW] - Assumed based on limited information

## Usage
Features:
- [HIGH] User authentication with email/password
- [MEDIUM] Social login (mentioned briefly)
- [LOW] Two-factor authentication (assumed for security)
```

---

## Z. Guardrails and Quality

### Z.1 Mode Enforcement

Every command declares its mode:

```markdown
**CLAVIX MODE: PRD**
Mode: planning
Purpose: Generating product requirements
Implementation: BLOCKED

Allowed Actions:
- Asking questions
- Writing documentation
- Analyzing requirements

Forbidden Actions:
- Writing code
- Executing commands
- Modifying source files
```

### Z.2 Command Boundaries

```markdown
## /clavix:improve boundaries
CAN:
- Analyze prompt structure
- Suggest improvements
- Save optimized version

CANNOT:
- Execute the prompt
- Write code
- Make API calls

## /clavix:implement boundaries
CAN:
- Write code
- Execute commands
- Modify files

CANNOT:
- Skip planning phase
- Ignore task checklist
- Modify outside scope
```

### Z.3 Quality Validation

```markdown
## PRD Quality Checklist
- [ ] Clear problem statement
- [ ] Defined user personas
- [ ] Measurable success criteria
- [ ] Bounded scope
- [ ] Identified dependencies
- [ ] Technical constraints stated

## Task Quality Checklist
- [ ] Actionable description
- [ ] Clear acceptance criteria
- [ ] Reasonable scope (< 4 hours)
- [ ] Dependencies identified
- [ ] Priority assigned
```

### Z.4 Verification Protocol

```markdown
## /clavix:verify checks
1. AUTOMATED
   - Test suite passes
   - Build succeeds
   - Linter passes
   - Types check

2. REQUIREMENTS
   - Each requirement mapped to implementation
   - Edge cases handled
   - Error cases covered

3. QUALITY
   - Code follows project standards
   - Documentation updated
   - No obvious security issues
```

### Z.5 Honest Limitations

From Clavix philosophy:

```markdown
## What Clavix Cannot Do
- Force agents to follow templates correctly
- Guarantee output quality
- Validate semantic correctness
- Replace human judgment
- Ensure agent compliance
```

---

## Sources and References

1. **Primary Repository**: https://github.com/ClavixDev/Clavix
2. **Official Website**: https://clavix.dev/
3. **Architecture Documentation**: https://github.com/ClavixDev/Clavix/blob/main/docs/architecture.md
4. **Commands Reference**: https://github.com/ClavixDev/Clavix/blob/main/docs/commands.md
5. **Integrations Guide**: https://github.com/ClavixDev/Clavix/blob/main/docs/integrations.md
6. **Contributing Guide**: https://github.com/ClavixDev/Clavix/blob/main/CONTRIBUTING.md
7. **npm Package**: https://www.npmjs.com/package/clavix

---

*Analysis generated via rcr-research:framework-analyzer skill with confirmed invocation*


---

<footer class="generation-meta">
<small>
Generated: 2025-12-02 21:28 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/clavix">Source Data</a>
</small>
</footer>