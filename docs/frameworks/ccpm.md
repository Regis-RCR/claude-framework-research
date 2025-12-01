---
title: CCPM (Claude Code PM)
category: 
layout: framework
---

# CCPM (Claude Code PM)

∵ RCR Regis ∴

**Category:** 
**Version:** 1.0.0
**Status:** Analyzed

## Scores

| Metric | Score | Rating |
|--------|-------|--------|
| SOLID Principles | 3.7/5.0 | ⭐⭐⭐☆☆ |
| Production Ready | 72/100 | 🟡 Beta |

### SOLID Breakdown

| Principle | Score | Notes |
|-----------|-------|-------|
| S - Single Responsibility | 4.0 | - |
| O - Open/Closed | 3.5 | - |
| L - Liskov Substitution | 3.5 | - |
| I - Interface Segregation | 4.0 | - |
| D - Dependency Inversion | 3.5 | - |

## Overview

*No description available.*




## Full Analysis

# CCPM (Claude Code PM) Framework Analysis

**Analysis Version:** 1.0.0
**Framework Version:** 1.0.0 (no official releases)
**Category:** methodology
**Analysis Date:** 2025-11-28
**Analyst:** Claude (via research-framework-analyzer skill)
**Skill Invocation:** Confirmed

---

## 1. Overview & Context

Claude Code PM (CCPM) is a specification-driven development system built by Automaze that fundamentally transforms how AI-assisted development workflows operate. Unlike traditional frameworks that treat AI agents as isolated code generators, CCPM positions GitHub Issues as a "distributed database" for coordinating multiple AI agents working in parallel through Git worktrees. The system enforces "No Vibe Coding" discipline, mandating that every line of code traces back to a specification through a structured 5-phase workflow.

With 5,484 GitHub stars accumulated within approximately 3 months since its August 2025 launch, CCPM positions itself as one of the fastest-growing Claude Code frameworks. The system's primary innovation lies in parallel spec-driven execution through Git worktrees, enabling development teams to manage 5-8 parallel tasks simultaneously while reportedly reducing bug rates by 75% and context-switching time by 89%.

The framework represents a project management paradigm built specifically for AI-native development, treating GitHub as native infrastructure rather than requiring separate project management tools. Its strength lies in comprehensive workflow orchestration from requirements through deployment, though this comes at the cost of significant setup overhead and a steep learning curve for teams unfamiliar with Git worktree workflows.

The zero-dependency architecture (pure shell scripts and markdown) creates both advantages (portability, security, simplicity) and constraints (limited cross-platform support, no package ecosystem). The framework operates entirely through files in a `.claude/` directory, requiring no package installation, compilation, or runtime dependencies beyond Git and Claude Code.

**Sources:**
- [GitHub Repository](https://github.com/automazeio/ccpm)
- [COMMANDS.md](https://github.com/automazeio/ccpm/blob/main/COMMANDS.md)
- [AGENTS.md](https://github.com/automazeio/ccpm/blob/main/AGENTS.md)

---

## 2. Architecture & Design

### 2.1 Component Architecture

CCPM implements a specification-driven coordination layer:

```
┌──────────────────────────────────────────────────────────────┐
│                        CCPM Core                              │
├──────────────────────────────────────────────────────────────┤
│  .claude/                                                     │
│  ├── CLAUDE.md           # Always-on instructions            │
│  ├── agents/             # 4 specialized agents              │
│  │   ├── code-analyzer/  # Bug hunting                       │
│  │   ├── file-analyzer/  # File summarization                │
│  │   ├── test-runner/    # Test execution                    │
│  │   └── parallel-worker/# Multi-stream coordinator          │
│  ├── commands/           # 28+ slash commands                │
│  │   ├── context/        # Project context management        │
│  │   ├── pm/             # Project management (core)         │
│  │   └── testing/        # Testing integration               │
│  ├── epics/              # Local workspace (gitignored)      │
│  ├── prds/               # Product Requirement Documents     │
│  └── rules/              # Reference rule files              │
└──────────────────────────────────────────────────────────────┘
```

**Three Core Architectural Principles:**

1. **GitHub as Native Infrastructure:** Issues serve as coordination database with built-in audit trails
2. **Worktrees as Isolation Boundaries:** Each agent works in isolated filesystem workspace
3. **Agents as Context Firewalls:** Heavy processing isolated from main conversation thread

### 2.2 Data Flow

5-phase specification-driven workflow:

```
Brainstorm → Document (PRD) → Plan (Epic) → Execute (Tasks) → Track
                  │               │              │
                  ▼               ▼              ▼
            .claude/prds/   .claude/epics/  Git Worktrees
                                   │              │
                                   ▼              ▼
                            GitHub Issues   Parallel Execution
```

**Parallel Execution Model:**
- Tasks decomposed into independent units
- Each task assigned to Git worktree
- Multiple AI agents execute simultaneously
- Merges happen only on task completion

### 2.3 Integration Points

1. **Slash Commands**: 28+ commands in markdown with YAML frontmatter
2. **GitHub Issues API**: Synchronization for distributed coordination
3. **Git Worktrees**: Parallel execution isolation
4. **Agent System**: 4 specialized agents for heavy processing
5. **File-Based Storage**: PRDs, epics, and context in markdown

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

CCPM provides comprehensive specification support:

**PRD Commands:**
- `/pm:prd-new`: Create Product Requirement Document with guided brainstorming
- `/pm:prd-parse`: Convert PRD to technical epic
- `/pm:prd-list`, `/pm:prd-edit`, `/pm:prd-status`: PRD management

**Epic Commands:**
- `/pm:epic-decompose`: Break epic into parallel tasks
- `/pm:epic-sync`: Push to GitHub Issues
- `/pm:epic-oneshot`: Combined decompose + sync

**Context Commands:**
- `/context:create`: Initialize project context
- `/context:update`: Refresh context files
- `/context:prime`: Load context into session

### 3.2 Execution Phase

Execution through parallel task isolation:

**Task Commands:**
- `/pm:issue-start`: Begin task in dedicated worktree
- `/pm:next`: Get next available task
- `/pm:issue-sync`: Sync progress to GitHub

**Agent Support:**
- `code-analyzer`: Bug hunting across codebase
- `file-analyzer`: Verbose file summarization
- `test-runner`: Test execution and analysis
- `parallel-worker`: Multi-stream coordination

### 3.3 Review Phase

Review integration through status tracking:

**Status Commands:**
- `/pm:status`: Overall progress dashboard
- `/pm:standup`: Daily standup report
- `/pm:blocked`: Report blockers
- `/pm:issue-close`: Complete task
- `/pm:epic-close`: Mark epic complete

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle

Clear separation: PRD commands handle requirements, epic commands handle planning, issue commands handle execution. Each agent has focused purpose (code-analyzer hunts bugs, test-runner executes tests).

**Score: 4.0/5.0**

### 4.2 Open-Closed Principle

Commands are markdown files enabling easy extension. New commands can be added without modifying existing ones. However, core workflow (5-phase) is rigid.

**Score: 3.5/5.0**

### 4.3 Liskov Substitution Principle

All commands follow consistent markdown+YAML frontmatter format. PRDs, epics, and tasks use consistent metadata patterns. Agents implement consistent invocation patterns.

**Score: 3.5/5.0**

### 4.4 Interface Segregation Principle

Commands segregated by category (pm/, context/, testing/). Users invoke only needed functionality. GitHub sync is optional (LOCAL_MODE supported).

**Score: 4.0/5.0**

### 4.5 Dependency Inversion Principle

Framework depends on Git and GitHub abstractions rather than specific implementations. Agent system depends on abstract task definitions. File-based storage provides flexible persistence.

**Score: 3.5/5.0**

### 4.6 Practical Examples

**SRP Example - Command Separation:**
```
/pm:prd-new      # Only PRD creation
/pm:epic-decompose # Only task breakdown
/pm:issue-start  # Only task execution
```

**OCP Example - Custom Commands:**
```
.claude/commands/custom/
└── my-workflow.md  # Add without modifying existing
```

**Overall SOLID Score:** 3.7/5.0

**Justification:** CCPM demonstrates reasonable SOLID adherence for a shell-script-based methodology framework. Single Responsibility manifests clearly in the command organization and agent specialization. Interface Segregation appears in command categorization and optional GitHub sync. Open-Closed is limited by the rigid 5-phase workflow but supported by extensible command system. The zero-dependency architecture creates natural abstraction boundaries. Lower scores reflect the inherent constraints of shell scripting versus structured programming languages.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**No Official Releases:** Despite 5,484 stars, no tagged versions exist. Rapid iteration without semantic versioning.

**Bug Factor:** High star-to-contributor ratio (609:1) suggests passive adoption. 38 open issues indicate ongoing concerns.

**Stability:** September 2025 stabilization sprint addressed bash syntax errors. Active maintenance but burst patterns.

**Score: 65/100**

### 5.2 Observability

**Status Tracking:** `/pm:status`, `/pm:standup` provide progress visibility.

**GitHub Integration:** Issue comments create comprehensive audit trails.

**Agent Outputs:** Agents return summaries preserving main conversation clarity.

**Score: 75/100**

### 5.3 Security

**Zero Dependencies:** No supply chain attack surface from packages.

**Local Execution:** All operations execute locally.

**GitHub API:** Optional; LOCAL_MODE supports offline operation.

**Score: 80/100**

### 5.4 Performance

**Parallel Execution:** Git worktrees enable 5-8 simultaneous tasks.

**Context Isolation:** Agents as "context firewalls" preserve main thread.

**No Overhead:** Zero dependencies mean no package loading delays.

**Score: 80/100**

### 5.5 Maintainability

**Documentation:** Comprehensive with bilingual support (English, Chinese).

**Bus Factor Risk:** 73.8% commits from single developer (ranaroussi).

**No Versioning:** Updates affect all users immediately without migration paths.

**Score: 60/100**

**Overall Production Score:** 72/100

---

## 6. Best Practices & Patterns

CCPM codifies several development patterns:

**Specification-Driven Development Pattern:** No code without traced requirements:
```
PRD → Epic → Task → Implementation → Verification
Every line traces back to documented requirement
```

**GitHub as Database Pattern:** Issues as coordination mechanism:
```
Issue #123: Task definition
  └── Comments: Decisions, progress, context
  └── Labels: Status, priority, assignee
  └── Links: Dependencies, related issues
```

**Worktree Isolation Pattern:** Parallel execution without conflicts:
```
main branch
├── worktree-1/ → task-branch-1
├── worktree-2/ → task-branch-2
└── worktree-3/ → task-branch-3
Agents work simultaneously, merge on completion
```

**Context Firewall Pattern:** Agents isolate heavy processing:
```
Main Conversation → Agent Invocation → Heavy Analysis
                                           ↓
                                     Summary Return
                 ← Only Essential Info ←
```

**5-Phase Discipline Pattern:**
1. Brainstorm: Explore requirements
2. Document: Create PRD
3. Plan: Decompose to epic/tasks
4. Execute: Parallel implementation
5. Track: Monitor and close

---

## 7. Limitations & Trade-offs

**No Official Releases:** Despite popularity, no semantic versioning. Updates can break existing workflows without warning.

**Steep Learning Curve:** Git worktree workflows unfamiliar to many developers. 5-phase discipline requires significant mindset shift.

**Bus Factor Risk:** 73.8% commits from single developer. Long-term maintenance uncertain.

**Cross-Platform Issues:** Shell-script architecture has known Windows problems despite PowerShell support.

**Overhead for Small Projects:** Specification discipline creates significant upfront investment unsuitable for rapid prototyping.

**Claude Code Dependency:** Framework completely tied to Anthropic's platform with no migration path.

**No Type Safety:** Shell scripts and markdown lack validation. Errors discovered at runtime rather than authoring time.

---

## 8. Community & Ecosystem

CCPM has achieved rapid but shallow community adoption:

**Adoption Metrics:** 5,484 stars in 3 months represents exceptional growth rate (~1,828/month).

**Contribution Gap:** Only 9 contributors despite high star count. 609:1 star-to-contributor ratio indicates passive adoption.

**Watcher Ratio:** 0.58% (32 watchers) unusually low, suggesting starred for reference rather than active following.

**Fork Activity:** 10.4% fork rate indicates experimentation, but only 1.6% contribute back upstream.

**Documentation Quality:** Comprehensive with COMMANDS.md, AGENTS.md, and bilingual README.

**Commercial Backing:** Automaze (automaze.io) provides organizational support.

---

## 9. Innovation & Differentiation

CCPM introduces several innovations:

**Parallel Spec-Driven Execution:** Git worktrees enable true parallelism without merge conflicts. Traditional sequential workflows bottleneck on single-agent execution; CCPM enables 5-8 simultaneous work streams.

**GitHub as Native Infrastructure:** Rather than external project management tools, CCPM uses Issues as the coordination database. Every decision lives in issue comments with built-in audit trails, access control, and version history.

**"No Vibe Coding" Discipline:** The 5-phase workflow enforces traceability from requirement to code. This creates upfront overhead but reportedly reduces bug rates by 75% and context-switching time by 89%.

**Agent Context Firewall Pattern:** Agents isolate heavy processing from main conversation, preserving context window for high-level decisions. This architectural pattern addresses a fundamental limitation of AI-assisted development.

**Zero-Dependency Architecture:** Pure shell scripts and markdown eliminate supply chain risks and enable instant portability. The framework can be copied to any system with Git and Claude Code.

**Offline-First Capability:** LOCAL_MODE supports complete offline operation, enabling privacy-sensitive work without external dependencies.

---

## 10. References & Sources

1. **GitHub Repository:** https://github.com/automazeio/ccpm
2. **COMMANDS.md:** Complete command reference
3. **AGENTS.md:** Agent architecture documentation
4. **LOCAL_MODE.md:** Offline workflow guide
5. **CONTEXT_ACCURACY.md:** Context generation safeguards
6. **Automaze:** https://automaze.io - Organization behind CCPM

---

## 11. Error Handling Patterns

### 11.1 Error Detection

**Command Validation:** YAML frontmatter specifies allowed tools, constraining agent behavior.

**Pre-Flight Checks:** Commands include explicit pre-flight verification steps.

**Context Verification:** CONTEXT_ACCURACY.md documents safeguards for context generation.

### 11.2 Error Recovery

**Worktree Isolation:** Task failures don't affect other parallel tasks or main branch.

**LOCAL_MODE:** Offline fallback when GitHub API unavailable.

**Git Recovery:** All changes versioned; rollback always possible.

### 11.3 Error Reporting

**Fail-Fast Design:** Commands include explicit error handling instructions.

**GitHub Comments:** Errors documented in issue comments for audit trail.

**Agent Summaries:** Agents return structured summaries including error conditions.

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

**Context Firewall Pattern:** Agents isolate heavy processing:
- Code analysis runs in agent
- Only summary returns to main conversation
- Preserves context for high-level decisions

**Worktree Parallelism:** Each agent gets focused context for its task rather than full project state.

**File-Based Context:** PRDs, epics, and context stored on disk; loaded selectively.

### 12.2 Context Management

**Selective Loading:** `/context:prime` loads relevant context for current work.

**Task Scoping:** Each task has focused scope reducing context requirements.

**Summary Compression:** Agent returns are compressed summaries not raw data.

---

## M. Methodology Principles

### M.1 The 5-Phase Discipline

CCPM enforces specification-driven development:

**Phase 1: Brainstorm**
- Explore requirements and possibilities
- Identify constraints and assumptions
- No commitment to solutions

**Phase 2: Document (PRD)**
- Structured requirements capture
- User stories, acceptance criteria
- Success metrics definition

**Phase 3: Plan (Epic)**
- Technical decomposition
- Task dependency mapping
- Parallel execution planning

**Phase 4: Execute (Tasks)**
- Git worktree isolation
- Parallel implementation
- GitHub Issue tracking

**Phase 5: Track**
- Progress monitoring
- Blocker identification
- Completion verification

### M.2 "No Vibe Coding" Philosophy

Every implementation decision traces to documented requirements:

**Traceability Chain:**
```
Requirement (PRD) → Task (Epic) → Code → Test → Verification
```

**Benefits:**
- 75% reported bug rate reduction
- 89% context-switching time reduction
- Full audit trail for compliance

### M.3 GitHub-Native Coordination

GitHub Issues as distributed database:

**Issue Structure:**
- Title: Task description
- Body: Detailed specification
- Comments: Decisions and progress
- Labels: Status and metadata
- Links: Dependencies and relations

**Advantages:**
- Built-in access control
- Version history for free
- No external tool dependencies
- Team collaboration ready


---

## Navigation

- [← Back to All Frameworks](index.md)
- [Comparison with similar frameworks](../comparisons/.md)
- [Full Synthesis](../synthesis.md)