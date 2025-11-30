---
title: ClaudeKit
category: domain-specific
layout: framework
---

# ClaudeKit

∵ RCR Regis ∴

**Category:** domain-specific
**Version:** 0.9.4
**Status:** Analyzed

## Scores

| Metric | Score | Rating |
|--------|-------|--------|
| SOLID Principles | 4.0/5.0 | ⭐⭐⭐⭐☆ |
| Production Ready | 81/100 | 🟢 Production |


## Overview

*No description available.*




## Full Analysis

# ClaudeKit - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-toolkit:research-framework-analyzer")
> - Template Version: 1.1
> - Category: domain-specific

**Framework:** ClaudeKit
**Version:** 0.9.4
**Category:** domain-specific
**Domain:** TypeScript/JavaScript Development
**Repository:** https://github.com/carlrannaberg/claudekit
**License:** MIT

---

## Table of Contents

1. [Overview & Context](#1-overview--context)
2. [Architecture & Design](#2-architecture--design)
3. [Development Cycle Integration](#3-development-cycle-integration)
4. [SOLID Principles Adherence](#4-solid-principles-adherence)
5. [Production Readiness Assessment](#5-production-readiness-assessment)
6. [Best Practices & Patterns](#6-best-practices--patterns)
7. [Limitations & Trade-offs](#7-limitations--trade-offs)
8. [Community & Ecosystem](#8-community--ecosystem)
9. [Innovation & Differentiation](#9-innovation--differentiation)
10. [References & Sources](#10-references--sources)
11. [Error Handling Patterns](#11-error-handling-patterns)
12. [Token Efficiency Analysis](#12-token-efficiency-analysis)
- [X. Domain Specialization Depth](#x-domain-specialization-depth)
- [Y. Integration with Domain Tools](#y-integration-with-domain-tools)
- [Z. Domain-Specific Best Practices](#z-domain-specific-best-practices)

---

## 1. Overview & Context

ClaudeKit is a mature and well-architected toolkit specifically designed for TypeScript/JavaScript development with Claude Code assistance. Created by Carl Rannaberg, an 18+ year CTO veteran formerly at Pipedrive, the framework provides intelligent guardrails, workflow automation, and expert subagents that act as a comprehensive safety net during AI-assisted coding sessions.

The framework addresses the critical need for domain-specific tooling in TypeScript/JavaScript development, offering capabilities that generic AI assistants cannot provide. With 399 GitHub stars, 45 forks, and 711 commits, ClaudeKit represents a mature solution that has evolved through real-world production usage across multiple projects.

ClaudeKit's core innovation lies in three key areas: (1) dynamic bash security analysis with 195+ patterns using actual syntax parsing rather than static pattern matching, (2) a non-destructive checkpoint system leveraging Git's low-level stash create/store commands, and (3) parallel multi-agent orchestration enabling 6+ specialist agents to write filesystem artifacts concurrently. These innovations collectively provide a safety layer that prevents common AI-assisted development pitfalls while maintaining development velocity.

The target audience is TypeScript/JavaScript developers using Claude Code Max plan who require enhanced safety guarantees, automated quality checks, and domain-specific expert assistance. The integration complexity is low-medium, requiring only npm installation and an interactive wizard that detects project structure and recommends relevant components.

As a pre-1.0 framework (0.9.x series), ClaudeKit is production-ready but continuing to evolve, with the commercial version (claudekit.cc) providing additional enterprise features beyond the open-source offering.

**Source:** [GitHub Repository](https://github.com/carlrannaberg/claudekit), [Official Documentation](https://docs.claudekit.cc/)

---

## 2. Architecture & Design

### 2.1 Component Architecture

ClaudeKit is structured as a modular AI development toolkit with three interconnected subsystems:

```
ClaudeKit Architecture
├── CLI System (claudekit, claudekit-hooks)
│   ├── Setup and project initialization
│   ├── Component discovery and installation
│   ├── Hook execution and monitoring
│   └── External LLM integration via prompt extraction
│
├── Hook System (Event-Driven)
│   ├── PreToolUse (validation before execution)
│   ├── PostToolUse (validation after changes)
│   ├── Stop (session completion)
│   ├── SubagentStop (specialized agent completion)
│   └── UserPromptSubmit (context injection)
│
└── Agent System (Hierarchical Delegation)
    ├── Triage Expert (problem routing)
    ├── Domain Specialists (TypeScript, React, NestJS, etc.)
    └── Cross-cutting Utilities (code-review, oracle)
```

**Configuration Files:**

| File | Purpose | Contents |
|------|---------|----------|
| `.claude/settings.json` | Hook-event bindings | Tool matcher patterns ("Write\|Edit\|MultiEdit") |
| `.claudekit/config.json` | Component settings | Customization options, agent configs |
| `CLAUDE.md` | Project conventions | Team standards, domain knowledge |
| `CLAUDE.local.md` | Personal overrides | User-specific settings (gitignored) |

### 2.2 Data Flow

ClaudeKit implements event-driven workflow automation:

```
User Prompt → UserPromptSubmit Hooks → Codebase Context Injection
      ↓
Claude Processing → PreToolUse Hooks → Security Validation
      ↓
Tool Execution → PostToolUse Hooks → Quality Checks (lint, typecheck, test)
      ↓
Session End → Stop Hooks → Final Validation + Checkpoint Creation
```

**Configuration Hierarchy (highest to lowest):**
1. Enterprise Level (organization-wide)
2. Project Level (`.claude/settings.json`)
3. User Level (`~/.claude/settings.json`)
4. Session Level (temporary overrides via `claudekit-hooks disable/enable`)

### 2.3 Integration Points

**IDE Integration:**
- Claude Code CLI (primary target)
- VS Code extension support
- Terminal-based workflows

**External Services:**
- npm registry for package distribution
- Git for checkpoint/rollback functionality
- TypeScript compiler for validation
- ESLint/Prettier for code quality

**External LLM Integration:**
```bash
# Extract agent prompt for use with any LLM
EXPERT=$(claudekit show agent typescript-expert)
cat code.ts | claude -p --append-system-prompt "$EXPERT" "Review"
```

**Source:** [DeepWiki Architecture Analysis](https://deepwiki.com/carlrannaberg/claudekit)

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

ClaudeKit supports specification-driven development through the `/spec:create` command:

```bash
/spec:create [feature-name]
```

**Capabilities:**
- Research existing codebase structure
- Generate comprehensive specifications
- Create implementation roadmaps
- Define acceptance criteria

The specification workflow detects overengineering patterns and warns about unnecessary abstractions, premature optimization, and suggests simpler alternatives.

### 3.2 Execution Phase

The 6-phase spec execution workflow (`/spec:execute [file]`):

```
Phase 1: Implementation
    └─ Generate code from spec

Phase 2: Test Writing
    └─ Create comprehensive tests

Phase 3: Code Review
    └─ 6-agent parallel analysis

Phase 4: Iterative Improvement
    └─ Address review findings

Phase 5: Commit
    └─ Atomic commits with standardized messages

Phase 6: Progress Tracking
    └─ Update task status
```

**Quality Gates:**
- Each phase includes validation before proceeding
- Dynamic agent selection based on file types
- Automatic fallbacks if agents unavailable

### 3.3 Review Phase

**Automated Quality Checks:**

| Hook | Trigger | Function |
|------|---------|----------|
| `typecheck-changed` | File modification | TypeScript validation |
| `lint-changed` | File modification | Linting checks |
| `test-changed` | File modification | Run relevant tests |
| `check-any-changed` | TypeScript files | Forbid `any` types |
| `check-comment-replacement` | Any edit | Detect code-to-comment substitutions |
| `check-unused-parameters` | Function changes | Identify lazy refactoring |

**Session-End Validation:**
- `typecheck-project` - Full TypeScript validation
- `lint-project` - Complete project linting
- `test-project` - Full test suite execution
- `create-checkpoint` - Automatic git-based checkpoint

**Source:** [ClaudeKit Documentation](https://docs.claudekit.cc/)

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle (SRP)

**Rating: Very Good (4/5)**

ClaudeKit demonstrates strong SRP adherence in its modular architecture:

**Evidence of Adherence:**
- Each hook has single, well-defined responsibility
  - `file-guard` - Only blocks sensitive file access
  - `typecheck-changed` - Only runs TypeScript validation
  - `create-checkpoint` - Only creates Git stash-based checkpoints
- Agent specialization - Each agent handles one domain
  - `typescript-expert` - TypeScript development only
  - `code-review-expert` - Code review orchestration only
  - `triage-expert` - Problem routing only

**Minor Violations:**
- Setup command combines multiple concerns (detection, recommendation, installation)
- Some CLI commands handle multiple responsibilities for UX convenience

### 4.2 Open-Closed Principle (OCP)

**Rating: Very Good (4/5)**

ClaudeKit excels at extensibility through its plugin architecture:

**Evidence of Adherence:**
- New agents added by creating `.md` files in `.claude/agents/`
- New hooks added by creating scripts in `.claude/hooks/`
- New commands added by creating files in `.claude/commands/`
- No source modification required for extensions

```bash
# Add custom agent without modifying source
echo "# Custom Expert\n..." > .claude/agents/custom-expert.md
# Auto-discovered at runtime
```

**Limitations:**
- Deeper customizations (file patterns, tool permissions) require source changes
- Storage backend not abstractable

### 4.3 Liskov Substitution Principle (LSP)

**Rating: Good (3.5/5)**

**Evidence of Adherence:**
- Hooks implement consistent interfaces
- Agents follow standard invocation patterns
- Tool permissions are consistently enforced

**Evidence of Violations:**
- Agent output formats vary (some return structured JSON, others plain text)
- Hook error handling inconsistent (some throw, some return error codes)

### 4.4 Interface Segregation Principle (ISP)

**Rating: Excellent (5/5)**

ClaudeKit exemplifies ISP through minimal, focused interfaces:

**Evidence of Adherence:**
- Each agent receives only tools it needs:
  - Read-only agents: `Read, Grep, Glob`
  - Research agents: `Read, Grep, Glob, WebFetch, WebSearch`
  - Code writers: `Read, Write, Edit, Bash, Glob, Grep`
- Granular hook events (PreToolUse, PostToolUse, Stop, SubagentStop)
- Focused CLI commands (separate binaries for different functions)

```javascript
// Perfect ISP - each agent gets minimal required tools
"typescript-expert": ["Read", "Write", "Edit", "Bash", "Glob", "Grep"]
"code-review-expert": ["Read", "Glob", "Grep"]  // No write access
```

### 4.5 Dependency Inversion Principle (DIP)

**Rating: Good (3.5/5)**

**Evidence of Adherence:**
- Configuration-based hook loading (hooks by name, not implementation)
- Dynamic agent directory discovery
- External LLM integration abstraction

**Evidence of Violations:**
- Direct CLI dependencies (`npx tsc`, `git stash`)
- File system direct access (`fs.readFileSync`)
- Claude Code platform lock-in

### 4.6 Practical Examples

**Example 1: Hook Specialization (SRP Excellence)**
```javascript
// file-guard.js - Single responsibility: block sensitive files
export default function fileGuard(toolUse) {
  const sensitivePatterns = ['.env', '.key', 'credentials'];
  if (sensitivePatterns.some(p => toolUse.path.includes(p))) {
    return { block: true, reason: 'Sensitive file access blocked' };
  }
  return { block: false };
}
```

**Example 2: Agent Extension (OCP Excellence)**
```markdown
# .claude/agents/custom-domain-expert.md

## Role
You are a domain-specific expert for [your domain].

## Tools
- Read, Write, Edit, Glob, Grep

## Guidelines
[Domain-specific instructions...]
```

**Example 3: Minimal Tool Permissions (ISP Excellence)**
```json
{
  "agents": {
    "code-review-expert": {
      "allowedTools": ["Read", "Glob", "Grep"],
      "deniedTools": ["Write", "Edit", "Bash"]
    }
  }
}
```

**Overall SOLID Score: 4.0/5.0**

**Justification:**
ClaudeKit demonstrates strong overall adherence to SOLID principles with exceptional ISP implementation (5/5) through minimal tool permissions per agent, granular hook events, and focused CLI commands. The framework's configuration-based extension system exemplifies OCP (4/5), enabling users to add agents, hooks, and commands without modifying source code. SRP (4/5) is well-implemented in the hook and agent architectures, with minor violations in CLI commands for UX convenience. The primary architectural weaknesses lie in LSP (3.5/5) through inconsistent agent output formats and DIP (3.5/5) through direct dependencies on external CLI tools (Git, TypeScript compiler). These issues reflect pragmatic design decisions prioritizing ease of implementation over theoretical purity. The 4.0/5.0 aggregate score positions ClaudeKit as having better SOLID adherence than most Claude Code frameworks, with clear paths for improvement in output standardization and tool abstraction.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**Score: 80/100**

**Strengths:**
- Non-destructive checkpoint system enables safe rollbacks
- Event-driven hooks provide consistent behavior
- 711 commits indicate mature, well-tested codebase

**Weaknesses:**
- Windows support is broken (critical platform gap)
- 8 unresolved issues without recent activity
- No visible test coverage metrics

### 5.2 Observability

**Score: 85/100**

**Strengths:**
- Built-in hook performance profiling with token estimation
- Session-based status tracking (`claudekit-hooks status`)
- 4-state system for hook visibility (enabled/disabled/not-configured/not-found)

```bash
claudekit-hooks status  # View all hook states
claudekit-hooks profile # Performance analysis
```

**Weaknesses:**
- No centralized logging dashboard
- Limited distributed tracing capabilities

### 5.3 Security

**Score: 90/100**

**Strengths:**
- 195+ bash security patterns with syntax analysis
- Defense in depth (5 security layers)
- Least privilege agent permissions
- Upload protection for data exfiltration prevention

**Security Layers:**

| Layer | Implementation | Protection |
|-------|----------------|------------|
| 1 | Input Validation | file-guard blocks sensitive files |
| 2 | Bash Analysis | Dynamic syntax parsing |
| 3 | Pattern Detection | 195+ risk patterns |
| 4 | Upload Protection | Tool-specific blocking |
| 5 | Checkpoint Recovery | Quick rollback capability |

### 5.4 Performance

**Score: 75/100**

**Strengths:**
- Context pollution reduced 40-60% through hierarchical scoping
- Incremental validation (only changed files)
- Parallel multi-agent execution

**Weaknesses:**
- Hook overhead on every tool use
- No caching for repeated validations
- Large codebase-map can slow first prompt

### 5.5 Maintainability

**Score: 80/100**

**Strengths:**
- Clear project structure
- Comprehensive documentation
- Modular hook and agent architecture

**Weaknesses:**
- Claude Code Max plan required
- 0 active PRs suggests limited external contributions
- Pre-1.0 status indicates API stability concerns

**Overall Production Score: 81/100**

ClaudeKit achieves strong production readiness for its target domain (TypeScript/JavaScript development) with exceptional security capabilities and comprehensive automation. The primary limitations are platform support (Windows broken) and community activity (low recent contributions).

---

## 6. Best Practices & Patterns

ClaudeKit implements several established patterns for AI-assisted development:

**Event-Driven Automation:**
- Hooks trigger on specific Claude Code events
- Enables non-intrusive quality enforcement
- Separates concerns between development and validation

**Defense in Depth:**
- Multiple security layers (input, analysis, patterns, upload, recovery)
- Each layer catches different threat categories
- No single point of security failure

**Least Privilege:**
- Agents receive minimal necessary permissions
- Read-only agents cannot modify code
- Research agents have web access but no write

**Checkpoint-Based Recovery:**
```bash
# Non-destructive checkpoint creation
git stash create                # Creates stash without modifying working tree
git stash store -m "msg" $hash  # Stores in reflog without clearing state

# Benefits:
# - Working directory remains untouched
# - Multiple checkpoints coexist
# - Rollback doesn't disrupt current work
```

**Session Isolation:**
- Temporary config overrides without permanent changes
- Clean separation of project/user/session settings
- Fuzzy matching for hook names

**Best Practice Recommendations:**
1. Enable `codebase-map` hook for instant project understanding
2. Use `file-guard` to protect sensitive files
3. Enable PostToolUse hooks for incremental validation
4. Create checkpoints before major refactoring
5. Use specialist agents for domain-specific tasks

---

## 7. Limitations & Trade-offs

**Critical Limitations:**

1. **Windows Support Broken**
   - Platform compatibility issue prevents Windows usage
   - Significant barrier for Windows-based teams
   - No timeline for resolution

2. **Claude Code Max Plan Required**
   - Full features require expensive subscription
   - Limits accessibility for individual developers
   - Commercial version adds additional cost

3. **Pre-1.0 API Stability**
   - API may change before 1.0 release
   - Breaking changes possible
   - Not suitable for long-term integrations

4. **Community Activity Concerns**
   - 8 unresolved issues, 0 visible closed
   - 0 active pull requests
   - Potential maintenance mode indicators

**Architectural Trade-offs:**

| Choice | Benefit | Cost |
|--------|---------|------|
| Git-based checkpoints | Non-destructive, reliable | Git required |
| Direct CLI dependencies | Simple implementation | No tool abstraction |
| Claude Code lock-in | Deep integration | Platform dependent |
| Session-based configs | Flexibility | Complexity |

**Not Recommended For:**
- Windows development teams
- Developers on Claude Code Free/Pro plans
- Non-TypeScript/JavaScript projects
- Teams requiring long-term API stability

---

## 8. Community & Ecosystem

**GitHub Statistics:**
- Stars: 399
- Forks: 45
- Contributors: ~5-10 active
- Total Commits: 711
- Open Issues: 8

**Ecosystem:**
- Commercial version: claudekit.cc
- Official documentation: docs.claudekit.cc
- npm package: claudekit

**Maintainer Background:**
Carl Rannaberg brings 18+ years CTO experience from Pipedrive, providing credible leadership and architectural expertise to the project.

**Agent Ecosystem:**

| Category | Agents |
|----------|--------|
| Language Experts | typescript-expert, react-expert |
| Infrastructure | database-expert, nestjs-expert, kafka-expert |
| Quality | code-review-expert, testing-expert |
| Cross-cutting | triage-expert, documentation-expert, oracle |

24+ specialized agents available covering TypeScript/JavaScript ecosystem comprehensively.

---

## 9. Innovation & Differentiation

ClaudeKit introduces several unique innovations in the Claude Code ecosystem:

**1. Dynamic Bash Security Analysis**
Unlike static pattern matching, ClaudeKit performs actual syntax analysis on bash commands:
- 195+ security patterns
- Context-aware risk assessment
- Prevents false positives from static matching

**2. Non-Destructive Checkpoint System**
Unique implementation using Git's low-level commands:
```bash
git stash create   # Creates stash without modifying working tree
git stash store    # Stores without clearing state
```
- Multiple checkpoints coexist
- Working directory remains untouched
- Clean integration with Claude's stop events

**3. Parallel Multi-Agent Orchestration**
6 specialist agents write to filesystem artifacts concurrently:
- Bypasses AI response size limits
- Enables comprehensive code review
- Parallel processing for speed

**4. Session-Based Hook Control**
```bash
claudekit-hooks disable typecheck-changed  # Temporary disable
claudekit-hooks enable typecheck           # Re-enable with fuzzy match
```
- No permanent configuration changes
- 4-state system visibility
- Per-session experimentation

**5. Hook Performance Profiling**
Built-in token estimation and performance analysis:
```bash
claudekit-hooks profile
```
- Identifies slow hooks
- Token cost estimation
- Optimization guidance

**Competitive Position:**
ClaudeKit is the most comprehensive TypeScript/JavaScript-specific toolkit for Claude Code, trading breadth (multi-language support) for depth (domain-specific excellence).

---

## 10. References & Sources

**Primary Sources:**
1. [GitHub Repository](https://github.com/carlrannaberg/claudekit)
2. [Official Documentation](https://docs.claudekit.cc/)
3. [Commercial Version](https://claudekit.cc/)
4. [DeepWiki Architecture Analysis](https://deepwiki.com/carlrannaberg/claudekit)

**Phase 2 Research:**
5. `phase2/analysis/claudekit-research.md` - Comprehensive deep research

**Technical References:**
6. [Claude Code Settings Documentation](https://docs.claude.com/en/docs/claude-code/settings)
7. [Git Stash Create/Store](https://stackoverflow.com/questions/28635989/what-is-the-purpose-of-git-stash-create-and-git-stash-store)

**Code References:**
8. `.claude/settings.json` - Hook configurations
9. `.claudekit/config.json` - Component settings
10. `.claude/agents/` - Agent definitions

---

## 11. Error Handling Patterns

### 11.1 Error Detection

ClaudeKit implements comprehensive error detection through hook-based validation:

**PreToolUse Hooks (Prevention):**
```json
{
  "PreToolUse": [{
    "matcher": "Bash",
    "hooks": ["bash-security"]
  }]
}
```
- Blocks risky commands before execution
- 195+ pattern-based detection
- Dynamic syntax analysis

**PostToolUse Hooks (Detection):**
```json
{
  "PostToolUse": [{
    "matcher": "Write|Edit|MultiEdit",
    "hooks": ["typecheck-changed", "lint-changed"]
  }]
}
```
- Catches errors immediately after changes
- Incremental validation (changed files only)
- Prevents error accumulation

### 11.2 Error Recovery

**Checkpoint-Based Recovery:**
```bash
/checkpoint:restore [id]  # Restore to previous state
/checkpoint:list          # View available checkpoints
```

**Automatic Recovery Mechanisms:**

| Failure Type | Recovery Mechanism |
|--------------|-------------------|
| Bad refactor | `/checkpoint:restore` |
| Test failures | Automatic notification, retry |
| Agent errors | Fallback to alternative agent |
| Build failures | Stop hook validation |

### 11.3 Error Reporting

**Self-Review Integration:**
The `self-review` hook includes randomized critical questions:
- Challenges assumptions
- Identifies potential issues
- Suggests alternatives

**Session Status Reporting:**
```bash
claudekit-hooks status
# Shows: enabled, disabled, not-configured, not-found
```

**Hook Performance Profiling:**
```bash
claudekit-hooks profile
# Identifies slow hooks and token costs
```

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

ClaudeKit reduces context pollution by 40-60% through:

**Hierarchical Context Scoping:**

| Level | Scope | Persistence |
|-------|-------|-------------|
| CLAUDE.md Central | Cross-sessions | Permanent |
| Session Context | Current session | Temporary |
| Artifact Filesystem | Per-agent | Session |
| Checkpoint Isolation | Per-snapshot | Until deleted |

**Codebase Map Optimization:**
```json
{
  "codebase-map": {
    "include": ["src/**", "lib/**"],
    "exclude": ["**/*.test.ts", "**/*.spec.ts"],
    "format": "dsl"
  }
}
```
- Selective inclusion reduces token overhead
- DSL format more efficient than verbose descriptions
- Automatic updates as code changes

### 12.2 Context Management

**Artifact Filesystem:**
- Large agent outputs written to filesystem
- Bypasses AI response token limits
- 6+ agents write concurrently

**Session Isolation:**
- Temporary overrides don't pollute permanent config
- Clean separation reduces cognitive overhead
- Checkpoint isolation enables independent states

**Incremental Validation:**
- Only changed files validated (not entire project)
- Significantly reduces token consumption
- PostToolUse hooks run on specific file patterns

---

## X. Domain Specialization Depth

### X.1 TypeScript/JavaScript Focus

ClaudeKit provides deep TypeScript/JavaScript ecosystem coverage:

**Language-Specific Agents:**
- `typescript-expert` - Advanced TypeScript patterns, type inference
- `react-expert` - React component patterns, hooks, state management
- `nestjs-expert` - NestJS architecture, decorators, modules
- `database-expert` - ORM patterns, query optimization

**Framework Support:**

| Framework | Agent | Capabilities |
|-----------|-------|--------------|
| React | react-expert | Components, hooks, state |
| NestJS | nestjs-expert | Modules, controllers, services |
| Express | backend-expert | Routes, middleware, error handling |
| Next.js | react-expert | SSR, API routes, optimization |

### X.2 Domain-Specific Validation

**TypeScript Validation:**
- `typecheck-changed` - Incremental type checking
- `check-any-changed` - Prevents `any` type introduction
- `check-unused-parameters` - Identifies lazy refactoring

**Code Quality:**
- `lint-changed` - ESLint/Prettier validation
- `test-changed` - Relevant test execution
- `check-comment-replacement` - Detects code-to-comment substitutions

### X.3 Domain Expertise Depth

The specialist agents provide deep domain knowledge:

**typescript-expert capabilities:**
- Advanced generic patterns
- Type inference optimization
- Discriminated unions
- Conditional types
- Template literal types

**react-expert capabilities:**
- Hook patterns and custom hooks
- Performance optimization (memo, useMemo, useCallback)
- State management patterns
- Component composition

---

## Y. Integration with Domain Tools

### Y.1 TypeScript Compiler Integration

ClaudeKit integrates deeply with TypeScript toolchain:

```bash
# Incremental type checking
npx tsc --noEmit --incremental

# Project-wide validation on session end
npx tsc --noEmit
```

**Hook Configuration:**
```json
{
  "PostToolUse": [{
    "matcher": "*.ts|*.tsx",
    "hooks": ["typecheck-changed"]
  }],
  "Stop": ["typecheck-project"]
}
```

### Y.2 Linting & Formatting

**ESLint Integration:**
```json
{
  "PostToolUse": [{
    "matcher": "Write|Edit",
    "hooks": ["lint-changed"]
  }]
}
```

**Prettier Integration:**
- Automatic formatting validation
- Consistent code style enforcement
- Integration with editor configurations

### Y.3 Testing Framework Integration

**Jest/Vitest Support:**
```json
{
  "PostToolUse": [{
    "matcher": "*.ts|*.tsx",
    "hooks": ["test-changed"]
  }]
}
```

- Run relevant tests on file changes
- Full test suite on session end
- Coverage tracking integration

---

## Z. Domain-Specific Best Practices

### Z.1 TypeScript Best Practices

ClaudeKit enforces TypeScript best practices:

**Type Safety:**
- `check-any-changed` prevents `any` type introduction
- Strict TypeScript configuration recommended
- Type inference optimization

**Code Quality Patterns:**
```typescript
// Encouraged: Discriminated unions
type Result<T> =
  | { success: true; data: T }
  | { success: false; error: string };

// Prevented: any type
// const data: any = fetchData(); // Blocked by hook
```

### Z.2 React Best Practices

**Component Patterns:**
- Functional components over class components
- Custom hooks for reusable logic
- Proper memoization (React.memo, useMemo, useCallback)

**State Management:**
- Context API for simple state
- External stores for complex state
- Proper dependency arrays in hooks

### Z.3 Project Structure Standards

**Recommended Structure:**
```
project-root/
├── .claude/
│   ├── settings.json     # Hook configurations
│   ├── agents/           # Custom agents
│   └── commands/         # Custom commands
├── .claudekit/
│   └── config.json       # ClaudeKit settings
├── src/
│   ├── components/       # React components
│   ├── hooks/            # Custom hooks
│   ├── services/         # Business logic
│   └── types/            # TypeScript types
├── CLAUDE.md             # Project conventions
└── CLAUDE.local.md       # Personal overrides
```

**Enforcement Hooks:**
- `file-guard` - Protect sensitive files
- `check-comment-replacement` - Prevent lazy refactoring
- `check-unused-parameters` - Maintain clean code

---

## Analysis Summary

| Metric | Value |
|--------|-------|
| **SOLID Score** | 4.0/5.0 |
| **Production Score** | 81/100 |
| **Category** | domain-specific |
| **Domain** | TypeScript/JavaScript |
| **Maturity** | Pre-1.0 (0.9.4) |
| **Template** | v1.1 |
| **Sections** | 15 (12 core + 3 domain-specific) |

**Key Strengths:**
- Deep TypeScript/JavaScript specialization with 24+ agents
- Exceptional security (195+ bash patterns, dynamic analysis)
- Non-destructive checkpoint system
- Strong SOLID adherence (4.0/5.0)
- Comprehensive hook system for quality automation

**Key Limitations:**
- Windows support broken
- Claude Code Max plan required
- Pre-1.0 API stability concerns
- Low community activity (8 open issues, 0 PRs)

**Recommendation:**
ClaudeKit is highly recommended for TypeScript/JavaScript development teams on macOS/Linux using Claude Code Max plan. The deep domain specialization, comprehensive security, and automated quality checks provide significant productivity and safety benefits. Not recommended for Windows users or teams requiring multi-language support.


---

## Navigation

- [← Back to All Frameworks](index.md)
- [Comparison with similar frameworks](../comparisons/domain-specific.md)
- [Full Synthesis](../synthesis.md)