---
title: MoAI-ADK (Agentic Development Kit)
layout: default
parent: Frameworks
---

# MoAI-ADK (Agentic Development Kit)

<div class="framework-meta">
<strong>Version:</strong> 0.30.2 |
<strong>Repository:</strong> <a href="https://github.com/modu-ai/moai-adk">GitHub</a> |
<strong>License:</strong> MIT
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: sdk</span>
<span class="badge badge-exec">exec: multi-agent</span>
<span class="badge badge-function">function: orchestration</span>
<span class="badge badge-ecosystem">ecosystem: python</span>
<span class="badge badge-scope">scope: project-level</span>
<span class="badge badge-integration">integration: code-integration</span>
<span class="badge badge-user">user: team, enterprise</span>
<span class="badge badge-complexity">complexity: high</span>
<span class="badge badge-maturity">maturity: beta</span>
<span class="badge badge-community">community: established</span>
<span class="badge badge-maintenance">maintenance: intensive</span>
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
<td>3.8/5.0 ⭐⭐⭐☆☆</td>
<td><strong>Overall</strong></td>
<td>79/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>4.0/5.0</td>
<td>Reliability</td>
<td>80</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>4.0/5.0</td>
<td>Observability</td>
<td>85</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>3.5/5.0</td>
<td>Security</td>
<td>90</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>4.0/5.0</td>
<td>Performance</td>
<td>75</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>3.5/5.0</td>
<td>Maintainability</td>
<td>65</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>SPEC-First with EARS format for structured requirements</li>
<li>TRUST 5 quality principles (Testable, Readable, Unified, Secured, Trackable)</li>
<li>32-agent specialization system with domain experts</li>
<li>Hybrid Personal-Pro Git workflow (auto-adapts to team size)</li>
<li>Agent Context Firewall pattern (80-85% token reduction)</li>
<li>MCP Integration Suite (Context7, Playwright, Figma)</li>
</ul>

## Best For

<ul class="compact-list">
<li>Enterprise Python development with TDD compliance</li>
<li>Projects requiring full requirement traceability</li>
<li>Teams enforcing 85%+ test coverage</li>
<li>Documentation automation workflows</li>
<li>Multi-agent orchestrated development</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Steep learning curve (3-5 day ramp-up, 85K+ words docs)</li>
<li>Python-only focus (limited non-Python support)</li>
<li>Claude Code CLI dependency (vendor lock-in)</li>
<li>TDD overhead slows prototyping (2-3x slower)</li>
<li>Bus factor risk (2 contributors, 99% single developer)</li>
<li>Token constraints for large codebases (200K limit)</li>
</ul>

---

## Full Analysis

# MoAI-ADK Framework Analysis

> **Analysis Metadata**
> - Date: 2025-12-01
> - Analyst: Claude (via framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-research:framework-analyzer")
> - Template Version: 1.1
> - Category: agentic-sdk

**Framework:** MoAI-ADK
**Version:** v0.30.2
**Category:** agentic-sdk
**Repository:** https://github.com/ai-1st/moai-adk
**License:** MIT

---

## 1. Overview & Context

MoAI-ADK (Agentic Development Kit) is a sophisticated Python-based framework that combines SPEC-First development methodology, Test-Driven Development (TDD), and AI agent orchestration to create a complete, traceable development lifecycle. Developed by ModuAI (modu-ai), the framework centers around "Alfred," a SuperAgent system with 32 specialized agents and 128+ skills designed to automate the entire software development process from requirements to documentation.

With 279 GitHub stars and 61 forks, MoAI-ADK represents one of the most comprehensive Claude Code frameworks for enterprise Python development. The core value proposition is enforcing "No Vibe Coding" discipline through a structured 5-phase workflow: Brainstorm → Document (PRD) → Plan (Epic) → Execute (Tasks) → Track.

Key differentiators include SPEC-First methodology with EARS format for structured requirements, automated RED-GREEN-REFACTOR TDD cycles with 85%+ coverage enforcement, TRUST 5 quality principles embedded throughout the workflow, and a Hybrid Personal-Pro Git workflow that auto-adapts based on team size. The 4-layer architecture (Commands → Sub-agents → Skills → Hooks) provides sophisticated orchestration.

The framework requires Python 3.11+ and the Claude Code CLI as runtime dependencies. The zero-dependency installation approach (pure Python with minimal requirements) ensures portability. The MIT license enables commercial use, making it accessible for enterprise development workflows requiring strict quality compliance.

**Sources:**
- [GitHub Repository](https://github.com/modu-ai/moai-adk)
- [Documentation Site](https://adk.mo.ai.kr)
- CLAUDE.md configuration file (v4.0)

---

## 2. Architecture & Design

### 2.1 Component Architecture

MoAI-ADK implements a 4-layer hierarchical architecture:

```
┌──────────────────────────────────────────────────────────────┐
│                    COMMANDS LAYER                            │
│  /alfred:0-project, :1-plan, :2-run, :3-sync                │
│  Workflow orchestration and user interaction                 │
├──────────────────────────────────────────────────────────────┤
│                   SUB-AGENTS LAYER (32)                      │
│  spec-builder, tdd-implementer, quality-gate, git-manager   │
│  Domain expertise delegation via Task()                      │
├──────────────────────────────────────────────────────────────┤
│                    SKILLS LAYER (128+)                       │
│  moai-lang-python, domain-backend, security-owasp           │
│  Knowledge capsules loaded on demand                         │
├──────────────────────────────────────────────────────────────┤
│                     HOOKS LAYER                              │
│  SessionStart, PreToolUse, UserPromptSubmit, SessionEnd     │
│  Guardrails, context injection, quality gates               │
└──────────────────────────────────────────────────────────────┘
```

**Directory Structure:**
```
.claude/
├── agents/alfred/          # 32 specialized agents
├── commands/               # Workflow commands (0-3)
├── hooks/                  # Lifecycle hooks
├── skills/                 # 128+ skill directories
└── settings.json           # Main configuration

.moai/
├── specs/                  # SPEC documents (EARS format)
├── config/                 # Framework configuration
├── reports/                # Generated reports
└── backups/                # Configuration backups
```

### 2.2 Data Flow

5-phase SPEC-driven workflow:

```
Brainstorm → Document (PRD) → Plan (Epic) → Execute (Tasks) → Track
                 │                 │              │
                 ▼                 ▼              ▼
          .moai/specs/       GitHub Issues   Git Worktrees
                                   │              │
                                   ▼              ▼
                           Coordination    RED-GREEN-REFACTOR
```

**TRUST 5 Quality Gates at Each Phase:**
- **T**est First: 85% coverage minimum, RED-GREEN-REFACTOR
- **R**eadable: Cyclomatic complexity ≤10, function length ≤50 lines
- **U**nified: Consistent architecture, standardized patterns
- **S**ecured: OWASP Top 10, Bcrypt 12-round, AES-256
- **T**rackable: TAG annotations, SPEC-linked commits

### 2.3 Integration Points

1. **Slash Commands**: 4 workflow commands (/alfred:0-3) with YAML frontmatter
2. **Agent Delegation**: Task(subagent_type='...') for 32 specialized agents
3. **MCP Integration**: Context7, Playwright, Sequential Thinking, Figma servers
4. **GitHub**: Issues as coordination database, PR workflows
5. **CI/CD**: 10 GitHub Actions workflows for automated quality gates

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

MoAI-ADK provides comprehensive specification support:

**Phase 0 - Project Initialization (`/alfred:0-project`):**
- INITIALIZATION: First-time setup
- AUTO-DETECT: Modify existing projects
- SETTINGS: Tab-based configuration
- Language-First Architecture (language selection before configuration)

**Phase 1 - Planning (`/alfred:1-plan`):**
- Explore agent discovers files and existing SPECs
- spec-builder proposes 1-3 SPEC candidates with EARS structure
- Creates spec.md, plan.md, acceptance.md in .moai/specs/SPEC-{ID}/
- Git branch setup: feature/SPEC-{ID}

### 3.2 Execution Phase

Core functionality centers on TDD-enforced execution:

**Phase 2 - Execution (`/alfred:2-run SPEC-XXX`):**
- implementation-planner creates TAG chains
- tdd-implementer executes RED-GREEN-REFACTOR cycles
- quality-gate verifies TRUST 5 compliance
- git-manager handles commits

**TDD Implementer Workflow:**
1. Plan Verification - Confirm and extract TAG chains
2. Environment Setup - Install libraries, validate frameworks
3. Iterative TAG Implementation - Execute TDD cycles
4. Progress Tracking - Record completion, identify dependencies
5. Final Verification - Full suite, coverage targets, handover

### 3.3 Review Phase

Review support through synchronization and status:

**Phase 3 - Synchronization (`/alfred:3-sync`):**
- `auto` - Smart selective sync with PR conversion (default)
- `force` - Full project re-sync for error recovery
- `status` - Health check without changes
- `project` - Integrated project-wide updates

**Status Commands:**
- `/pm:status` - Overall progress dashboard
- Coverage reports with Codecov integration
- Quality gate verification results

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle

Clear agent separation: spec-builder handles specifications, tdd-implementer handles TDD cycles, quality-gate handles verification, git-manager handles Git operations. Each of the 32 agents has single, focused responsibility. File limits (300 lines) and function limits (50 lines) enforce modularity.

**Score: 4.0/5.0**

### 4.2 Open-Closed Principle

128+ skills provide extensibility without modification. Agent factory enables new agent creation. Skill factory supports custom skill development. New workflows can be added through slash commands without modifying core. However, the 5-phase workflow itself is relatively rigid.

**Score: 4.0/5.0**

### 4.3 Liskov Substitution Principle

Consistent agent interface via `Task(subagent_type='...')`. All agents follow standard invocation patterns. Skill loading follows consistent patterns across domains. The quality-gate agent can substitute for different verification types.

**Score: 3.5/5.0**

### 4.4 Interface Segregation Principle

Specialized agents: backend-expert, frontend-expert, database-expert each handle distinct domains. Skills organized by category (lang-python, domain-backend, security-owasp). Users invoke only needed functionality; GitHub sync is optional (LOCAL_MODE supported).

**Score: 4.0/5.0**

### 4.5 Dependency Inversion Principle

Agent delegation pattern (Commands → Agents → Skills) provides abstraction layers. Context7 MCP abstracts documentation sources. Git operations abstracted through git-manager agent. Quality verification abstracted through quality-gate agent.

**Score: 3.5/5.0**

### 4.6 Practical Examples

**SRP Example - Agent Specialization:**
```python
# Each agent handles one domain
Task(subagent_type='spec-builder')      # Requirements only
Task(subagent_type='tdd-implementer')   # TDD cycles only
Task(subagent_type='quality-gate')      # Verification only
Task(subagent_type='git-manager')       # Git operations only
```

**OCP Example - Skill Extension:**
```
.claude/skills/
├── moai-lang-python/     # Python expertise
├── moai-lang-rust/       # Add new language without modifying existing
├── domain-backend/       # Domain expertise
└── custom-skill/         # User-defined extensions
```

**Overall SOLID Score:** 3.8/5.0

**Justification:** MoAI-ADK demonstrates strong SOLID adherence throughout its Python codebase. The 32-agent architecture naturally enforces Single Responsibility through clear domain boundaries. The 128+ skill system exemplifies Open-Closed by enabling new capability integration without modifying existing code. Interface Segregation appears in the specialized agent organization and domain-specific skill categorization. The Task() delegation pattern provides Dependency Inversion through abstraction layers. Lower scores reflect the rigid 5-phase workflow structure and the complexity of understanding the full agent ecosystem.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**Active Development:** 12 releases in 5 days (v0.25.0-v0.25.11). 100% test pass rate (315/315 tests).

**Pre-1.0 Status:** Still approaching 1.0 release, but zero breaking changes in recent versions.

**Issue Resolution:** 100% resolution rate across 232+ issues. Critical issues resolved within 24 hours.

**Score: 80/100**

### 5.2 Observability

**Logging:** Comprehensive logging to .moai/logs with configurable retention (30 days).

**Monitoring:** monitoring-expert agent provides 5-minute detection time, 80%+ alert noise reduction.

**Debug Support:** debug-helper agent with 95% root cause accuracy, 70% resolution time reduction.

**Built-in Commands:** /cost, /usage, /context, /memory for real-time observability.

**Score: 85/100**

### 5.3 Security

**OWASP Compliance:** Full OWASP Top 10 (2024) compliance enforcement.

**Cryptography:** Bcrypt 12-round, AES-256 at rest, TLS 1.3+ in transit.

**Scanning:** CVE scanning via pip-audit, Dependabot, Bandit security scanning.

**Zero Vulnerabilities:** No disclosed CVEs as of v0.25.11.

**Score: 90/100**

### 5.4 Performance

**Token Efficiency:** 80-85% token reduction via agent delegation. Haiku for speed, Sonnet for reasoning.

**Caching:** 24-hour caching for version checks (200-400ms → 10-20ms).

**Constraints:** 200,000 token budget may be insufficient for very large codebases (>100K LOC).

**Score: 75/100**

### 5.5 Maintainability

**Test Coverage:** 85%+ enforced with CI/CD blocking below threshold.

**Type Safety:** 100% type hint coverage with mypy strict mode.

**Contributor Concentration:** 2 contributors with 99% commits from core team. Bus factor risk.

**Documentation Volume:** 85,280+ words can overwhelm newcomers.

**Score: 65/100**

**Overall Production Score:** 79/100

---

## 6. Best Practices & Patterns

MoAI-ADK codifies several enterprise development patterns:

**SPEC-First with EARS Format Pattern:**
```yaml
# .moai/specs/SPEC-001/spec.md
id: SPEC-001
title: Feature Implementation
ears_format:
  when: User performs action
  the_system_shall: Respond appropriately
  so_that: Business value is delivered
```

**Agent Delegation Pattern:**
```python
# Commands delegate to specialized agents
Task(subagent_type='spec-builder')     # Requirements
Task(subagent_type='tdd-implementer')  # Implementation
Task(subagent_type='quality-gate')     # Verification
# Never call agent methods directly
```

**TRUST 5 Quality Gate Pattern:**
```
T: Test First   → 85% coverage, RED-GREEN-REFACTOR
R: Readable     → Complexity ≤10, length ≤50 lines
U: Unified      → Consistent patterns, no circular imports
S: Secured      → OWASP Top 10, CVE scanning
T: Trackable    → TAG annotations, SPEC-linked commits
```

**Hybrid Git Workflow Pattern:**
```
Personal Mode (1-2 devs):
  main → feature/SPEC-{ID} → direct merge
  Release cycle: ~10 minutes

Team Mode (3+ devs):
  develop → feature/SPEC-{ID} → PR review → merge
  Release cycle: ~30 minutes with QA gates
```

---

## 7. Limitations & Trade-offs

**Steep Learning Curve:** 5-phase workflow, 32 agents, 128+ skills require significant onboarding. Reported 3-5 day ramp-up period. 85,280+ words of documentation.

**Python-Only Focus:** Framework optimized exclusively for Python development. Limited non-Python language integration. JavaScript/Node.js projects require workarounds.

**Claude Code Dependency:** Requires Claude Code CLI as runtime dependency. Vendor lock-in to Anthropic's platform. No API-first architecture for custom integrations.

**TDD Overhead:** Mandatory test-first approach incompatible with rapid prototyping. RED-GREEN-REFACTOR ceremony slows exploratory development by 2-3x.

**Bus Factor Risk:** 2 contributors with 99% commits from single developer (GoosLab). Long-term maintenance dependent on continued commitment.

**Token Constraints:** 200,000 token budget may be insufficient for monolithic large codebases (>100K LOC).

---

## 8. Community & Ecosystem

MoAI-ADK has a focused but active community:

**Adoption Metrics:** 279 stars, 61 forks, 3,004+ commits indicate substantial codebase maturity.

**Contributor Base:** 2 contributors—concentrated but highly active.

**Issue Resolution:** 100% resolution rate with critical issues addressed within 24 hours.

**Release Velocity:** 12 releases in 5 days (v0.25.0-v0.25.11) demonstrates active maintenance.

**International Interest:** Japanese translation PR indicates international market resonance.

**Documentation:** Comprehensive with CLAUDE.md v4.0, COMMANDS.md, AGENTS.md, and bilingual README.

---

## 9. Innovation & Differentiation

MoAI-ADK introduces several innovations:

**SPEC-First with EARS Format:** Structured requirements using EARS (Easy Approach to Requirements Syntax) format before any code is written. Every line of code traces back to a documented specification, enforcing "No Vibe Coding" discipline.

**TRUST 5 Quality Principles:** Five embedded quality dimensions (Testable, Readable, Unified, Secured, Trackable) enforced at every workflow stage through automated gates.

**32-Agent Specialization System:** Domain experts (backend-expert, frontend-expert, database-expert), process agents (spec-builder, tdd-implementer), and support agents (debug-helper, monitoring-expert) provide comprehensive coverage.

**Hybrid Personal-Pro Git Workflow:** Auto-adapts from direct merges (1-2 devs) to PR-based Git-Flow (3+ devs) based on team size, with automatic checkpoint system for safe rollback.

**Agent Context Firewall Pattern:** Heavy processing isolated in sub-agents, returning only summaries to main conversation. Achieves 80-85% token reduction while maintaining context clarity.

**MCP Integration Suite:** Context7 for documentation, Playwright for browser automation, Sequential Thinking for reasoning, Figma for design integration—all through unified MCP protocol.

---

## 10. References & Sources

1. **GitHub Repository:** https://github.com/modu-ai/moai-adk
2. **Documentation Site:** https://adk.mo.ai.kr
3. **PyPI Package:** https://pypi.org/project/moai-adk/
4. **CLAUDE.md:** v4.0 integration guide
5. **COMMANDS.md:** Workflow command reference
6. **AGENTS.md:** 32-agent specifications

---

## 11. Error Handling Patterns

### 11.1 Error Detection

**Quality Gate Verification:** quality-gate agent evaluates TRUST 5 dimensions with PASS/WARNING/CRITICAL levels.

**Pre-Flight Checks:** Commands include explicit pre-flight verification steps.

**Hook Validation:** PreToolUse hooks validate operations before execution.

### 11.2 Error Recovery

**Checkpoint System:** Automated backups on critical actions enable safe rollback.

**Worktree Isolation:** Task failures don't affect other parallel tasks or main branch.

**MCP Fallback:** Manual WebFetch-based research when Context7 unavailable.

### 11.3 Error Reporting

**Debug Helper:** AI-DEBUG framework with 95% root cause accuracy, 70% resolution time reduction.

**GitHub Comments:** Errors documented in issue comments for audit trail.

**Agent Summaries:** Structured summaries including error conditions and suggested corrections.

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

**Agent Context Firewall:** Heavy processing in sub-agents, only summaries returned. 80-85% token reduction.

**Model Selection Strategy:** Haiku for speed-critical tasks, Sonnet for reasoning, Inherit for balanced.

**Selective Skill Loading:** Only relevant skills loaded per agent invocation from 128+ options.

### 12.2 Context Management

**200K Token Budget:** Configured maximum for context optimization.

**Skill Lazy Loading:** Skills loaded on demand rather than monolithically.

**Summary Compression:** Agent returns compressed summaries, not raw analysis.

---

## A. Agentic Architecture

### A.1 Agent Roster (32 Specialized Agents)

**Development & Architecture:**
- api-designer: API schema design
- backend-expert: Backend architecture patterns
- frontend-expert: Frontend patterns and state management
- component-designer: Component architecture
- database-expert: Database design and optimization

**Quality & Testing:**
- quality-gate: TRUST 5 enforcement
- tdd-implementer: RED-GREEN-REFACTOR execution
- debug-helper: Error diagnosis and resolution
- performance-engineer: Optimization strategies

**DevOps & Infrastructure:**
- devops-expert: CI/CD, containers, deployment
- monitoring-expert: Observability and alerting
- migration-expert: Migration strategies

**Project Management:**
- project-manager: Coordination and planning
- implementation-planner: Task decomposition
- spec-builder: EARS specifications

**Integration:**
- mcp-context7-integrator: Documentation lookup
- mcp-playwright-integrator: Browser automation
- mcp-figma-integrator: Design system integration

### A.2 Agent Delegation Protocol

**Correct Usage:**
```python
# Via Task delegation (REQUIRED)
Task(subagent_type='tdd-implementer')
Task(subagent_type='quality-gate')
```

**Forbidden:**
```python
# Direct execution (PROHIBITED)
# agent.execute()  # Never call directly
```

### A.3 Agent Factory System

**Three-Tier Template System:**
- **Tier 1 (Simple):** ~200 lines, Haiku model, utilities
- **Tier 2 (Standard):** 200-500 lines, Sonnet, domain experts
- **Tier 3 (Complex):** 500+ lines, Sonnet, orchestrators

**Model Selection Algorithm:**
- Sonnet: Complexity >= 7 or research-heavy
- Haiku: Speed-critical, low-complexity
- Inherit: Mixed requirements (5-7 complexity)

### A.4 Skill Categories (128+ Skills)

**Core Framework (36 skills):**
- Alfred System: Workflow, configuration, code review
- Claude Configuration: MCP, memory, settings
- Foundation: Git, language, specifications, TRUST 5

**Domain Expertise:**
- Backend, Cloud, DevOps, Database, Monitoring
- Frontend, Figma, Shadcn UI
- Data Science, ML, ML-Ops
- Testing, Security, Web API, Mobile

**Language Support (18+ languages):**
Python, JavaScript, TypeScript, Java, C++, C#, Go, Rust, PHP, Ruby, Kotlin, Swift, Dart, Scala, Shell, SQL, HTML/CSS, Tailwind CSS

**BaaS Integrations (12 platforms):**
Firebase, Supabase, Vercel, Railway, Convex, Cloudflare, Auth0, Clerk, Neon


---

<footer class="generation-meta">
<small>
Generated: 2025-12-01 22:56 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/moai-adk">Source Data</a>
</small>
</footer>