---
title: SuperClaude
category: 
layout: framework
---

# SuperClaude

∵ RCR Regis ∴

**Category:** 
**Version:** 4.1.9
**Status:** Analyzed

## Scores

| Metric | Score | Rating |
|--------|-------|--------|
| SOLID Principles | 4.1/5.0 | ⭐⭐⭐⭐☆ |
| Production Ready | 73/100 | 🟡 Beta |

### SOLID Breakdown

| Principle | Score | Notes |
|-----------|-------|-------|
| S - Single Responsibility | 4.5 | - |
| O - Open/Closed | 4.5 | - |
| L - Liskov Substitution | 4.0 | - |
| I - Interface Segregation | 4.5 | - |
| D - Dependency Inversion | 3.0 | - |

## Overview

*No description available.*




## Full Analysis

# SuperClaude - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-toolkit:research-framework-analyzer")
> - Template Version: 1.1
> - Category: methodology

## 1. Executive Summary

SuperClaude is a meta-programming configuration framework that transforms Claude Code into a structured development platform through behavioral instruction injection and component orchestration. With 18.4k GitHub stars and a mature v4.1.9 release, it has established itself as a leading methodology framework in the Claude ecosystem, offering 30 slash commands, 16 specialized AI personas, and 7 behavioral modes.

**Key Value Proposition**: Programs Claude Code through structured prompts and context files rather than external tooling, creating an ecosystem of interconnected configurations that shape Claude's responses, priorities, and methodologies.

**Primary Innovation**: Behavioral instruction injection - the insight that Claude Code can be "programmed" through specialized context files that load when commands are invoked, enabling domain-specific expertise without code modifications.

## 2. Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                   CONFIGURATION LAYER                            │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              ~/.claude/ Directory Structure               │   │
│  │  ├── commands/          (30 slash commands)              │   │
│  │  ├── personas/          (16 AI personas)                 │   │
│  │  ├── modes/             (7 behavioral modes)             │   │
│  │  └── RULES.md           (Evidence-based methodology)     │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                   COMMAND SYSTEM                                 │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │               30 Slash Commands                           │   │
│  │                                                           │   │
│  │  Development    │  Analysis     │  Quality                │   │
│  │  ─────────────  │  ──────────   │  ────────               │   │
│  │  /build         │  /analyze     │  /review                │   │
│  │  /scaffold      │  /explain     │  /audit                 │   │
│  │  /refactor      │  /document    │  /test                  │   │
│  │  /fix           │  /research    │  /security              │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                   PERSONA SYSTEM                                 │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐   │
│  │    PM      │ │  Security  │ │  Frontend  │ │   DevOps   │   │
│  │   Agent    │ │  Engineer  │ │  Architect │ │  Engineer  │   │
│  └────────────┘ └────────────┘ └────────────┘ └────────────┘   │
│  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐   │
│  │   Deep     │ │  Backend   │ │    QA      │ │   Data     │   │
│  │ Researcher │ │  Engineer  │ │  Engineer  │ │  Analyst   │   │
│  └────────────┘ └────────────┘ └────────────┘ └────────────┘   │
│                    + 8 more specialized personas                 │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                   BEHAVIORAL MODES                               │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │  Brainstorming │ Business │ Deep Research │ Orchestration │  │
│  │  Token-Efficient │ Task Management │ Introspection        │  │
│  └───────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                   MCP INTEGRATION (Optional)                     │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐               │
│  │ Tavily  │ │Context7 │ │ Serena  │ │Playwright│               │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘               │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐               │
│  │Sequential│ │  Magic  │ │Morphllm │ │ Chrome  │               │
│  │Thinking │ │         │ │FastApply│ │DevTools │               │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘               │
│                 (2-3x faster, 30-50% fewer tokens)              │
└─────────────────────────────────────────────────────────────────┘
```

**Architecture Pattern**: Configuration-as-code with behavioral injection

The architecture layers configuration files that inject specialized behavior into Claude Code without external runtime dependencies, making the framework purely additive to Claude's native capabilities.

## 3. Core Components

### 3.1 Command System (30 Commands)
- **Development**: /build, /scaffold, /refactor, /fix, /implement
- **Analysis**: /analyze, /explain, /document, /research
- **Quality**: /review, /audit, /test, /security
- **Management**: /plan, /estimate, /prioritize

### 3.2 Persona System (16 Personas)
- **Technical**: Security Engineer, Frontend Architect, Backend Engineer, DevOps
- **Product**: PM Agent, UX Designer, Data Analyst
- **Research**: Deep Researcher (autonomous web research)
- **Specialized**: QA Engineer, Performance Engineer, Accessibility Expert

### 3.3 Behavioral Modes (7 Modes)
- **Brainstorming**: Creative exploration mode
- **Business Panel**: Stakeholder-focused analysis
- **Deep Research**: Autonomous investigation mode
- **Orchestration**: Multi-task coordination
- **Token-Efficient**: Compressed output mode
- **Task Management**: Project planning focus
- **Introspection**: Self-analysis mode

### 3.4 RULES.md System
- **Purpose**: Evidence-based methodology enforcement
- **Key Rule**: AI must back up claims with proof
- **Effect**: Requires official documentation lookup before suggestions

## 4. Design Patterns

### 4.1 Behavioral Injection Pattern
Commands load context files that modify Claude's behavior:
```
/security invoked
  → loads ~/.claude/personas/security-engineer.md
  → activates security-focused response patterns
  → enables vulnerability detection workflows
```

### 4.2 Composition Pattern
Multiple components combine for specialized behavior:
```
/build --persona-architect --mode-efficient
  → combines build command + architect persona + token-efficient mode
```

### 4.3 Evidence-Based Pattern
RULES.md enforces proof requirements:
```
Before suggesting: "Use React hooks"
Must: Look up official React docs
Then: Cite specific documentation
```

### 4.4 Progressive Enhancement Pattern
MCP servers optionally enhance capabilities:
- Without MCPs: Full functionality via slash commands
- With MCPs: 2-3x faster, 30-50% token reduction

## 5. Strengths

1. **Large Community**: 18.4k stars, active development
2. **Zero Dependencies**: Pure configuration, no runtime requirements
3. **Token Optimization**: 70% reduction pipeline for large projects
4. **Evidence-Based**: RULES.md enforces documentation-backed suggestions
5. **Progressive Enhancement**: Works without MCPs, enhanced with them
6. **Comprehensive Coverage**: 30 commands cover full development lifecycle
7. **Persona Flexibility**: 16 specialized personas for domain expertise
8. **Local Execution**: 100% local, no third-party servers or data collection
9. **Simple Installation**: Single script install to ~/.claude/

## 6. Limitations

1. **TypeScript Plugin Delayed**: v5.0 plugin system not yet available
2. **Configuration Complexity**: 30 commands + 16 personas requires learning
3. **No Team Features**: Single-user focused, no collaboration
4. **Claude Code Specific**: Doesn't work with other AI assistants
5. **Version Fragmentation**: Multiple forks (NomenAK, Daerkle, gwendall)
6. **MCP Setup Complexity**: 8 optional MCPs require separate configuration
7. **Documentation Gaps**: Some advanced features underdocumented
8. **No State Persistence**: Session context not preserved

## 7. Production Readiness

### SOLID Score: 4.1/5.0

**Justification**: SuperClaude demonstrates strong Single Responsibility Principle through its clear separation of commands, personas, and modes - each file has one specific purpose. The 30 commands are individually focused (build builds, analyze analyzes, etc.). Open/Closed Principle is well-supported - new personas can be added without modifying existing code, and the --persona flag system allows extension without modification. The @include reference system enables composition without coupling. Liskov Substitution is applicable at the persona level - any persona can be substituted for another without breaking the command system structure. Interface Segregation is excellent - the flag system (--persona-X, --mode-Y) allows users to compose exactly the capabilities needed without loading unnecessary context. Users aren't forced to use all 16 personas or 7 modes. Dependency Inversion is partially achieved - commands depend on abstract persona interfaces rather than concrete implementations, but the tight coupling to Claude Code's specific features limits full DIP adherence. The optional MCP layer demonstrates good DIP by abstracting external services. Minor deductions for the configuration file coupling and Claude Code platform dependency.

### Production Score: 73/100

| Dimension | Score | Notes |
|-----------|-------|-------|
| Reliability | 78 | Stable v4.1.9, mature command system, graceful MCP fallback |
| Observability | 65 | Command output logging, but limited metrics/tracing |
| Security | 80 | 100% local execution, no data collection, evidence-based methodology |
| Performance | 75 | 70% token reduction, optional MCP acceleration (2-3x faster) |
| Maintainability | 68 | Configuration-as-code is clean, but 30 commands spread complexity |

## 8. Comparative Analysis

### vs BMAD Method
- **SuperClaude**: 30 commands + 16 personas, configuration-based
- **BMAD**: 19 agents + 50 workflows, document sharding
- **Winner**: SuperClaude for simplicity; BMAD for structured methodology

### vs Claude Code Native
- **SuperClaude**: Specialized commands, personas, evidence-based rules
- **Claude Code**: General assistant, no methodology enforcement
- **Winner**: SuperClaude for structured development; Native for ad-hoc

### vs Task Master
- **SuperClaude**: Command-based methodology, persona specialization
- **Task Master**: Task-based PRD parsing, dependency management
- **Winner**: SuperClaude for methodology; Task Master for task tracking

### vs RIPER-5
- **SuperClaude**: 30 commands, 7 modes, 16 personas
- **RIPER-5**: 5 phases, minimal complexity
- **Winner**: SuperClaude for power users; RIPER-5 for simplicity

## 9. Integration Patterns

### 9.1 Basic Installation
```bash
git clone https://github.com/SuperClaude-Org/SuperClaude_Framework.git
cd SuperClaude_Framework
./install.sh
```

### 9.2 With MCP Enhancement
```bash
# Install base
superclaude install

# Add MCP servers for acceleration
superclaude mcp setup
```

### 9.3 Persona Activation
```bash
# Activate specific persona for session
/analyze --persona-security
/build --persona-architect
/review --persona-qa
```

### 9.4 Mode Combination
```bash
# Combine modes for specialized behavior
/research --mode-deep-research --persona-researcher
/build --mode-efficient --persona-devops
```

## 10. Best Practices

1. **Start with Core Commands**: Learn /build, /analyze, /review before expanding
2. **Match Persona to Task**: Use security persona for audits, architect for design
3. **Enable Evidence Mode**: Keep RULES.md active for documentation-backed suggestions
4. **Use Token-Efficient Mode**: For large projects, enable compression
5. **Add MCPs Incrementally**: Start without MCPs, add as needed
6. **Document Custom Personas**: Track any persona modifications
7. **Update Regularly**: Keep framework current for latest commands
8. **Review Command Output**: Don't blindly accept suggestions

## 11. Configuration Reference

### Installation Options
| Method | Command |
|--------|---------|
| Git Clone | `git clone + ./install.sh` |
| Pipx | `pipx install superclaude` |
| Update | `superclaude update` |

### Command Categories
| Category | Commands | Purpose |
|----------|----------|---------|
| Development | 10 | Building, scaffolding, implementation |
| Analysis | 8 | Code analysis, documentation |
| Quality | 7 | Review, testing, security |
| Management | 5 | Planning, estimation |

### Behavioral Modes
| Mode | Purpose | Token Impact |
|------|---------|--------------|
| Brainstorming | Creative exploration | +20% |
| Token-Efficient | Compressed output | -50% |
| Deep Research | Autonomous investigation | +30% |
| Orchestration | Multi-task coordination | +10% |

## 12. Recommendations

### For Adoption
1. **Start with Installation**: Single script, zero dependencies
2. **Learn 5 Core Commands**: /build, /analyze, /review, /fix, /document
3. **Try 3 Personas**: Security, Architect, DevOps
4. **Enable RULES.md**: For evidence-based methodology

### For Enhancement
1. **Add v5.0 Plugin System**: TypeScript extensibility (planned)
2. **Improve Team Features**: Multi-user support
3. **Consolidate Forks**: Unify fragmented repositories
4. **Enhance Documentation**: Cover advanced command combinations

### For Production
1. **Lock to v4.1.9**: Use stable release
2. **Configure MCPs**: For performance-critical projects
3. **Audit Commands**: Review which commands team uses
4. **Monitor Token Usage**: Track efficiency gains

---

## METHODOLOGY EXTENSIONS

### X. Workflow Definition

```
PHASE 1: PROJECT SETUP
├── Command: /scaffold
├── Persona: Architect
├── Input: Project requirements
├── Output: Initial project structure
└── Validation: Structure matches requirements

PHASE 2: IMPLEMENTATION
├── Command: /build, /implement
├── Persona: Frontend/Backend as needed
├── Input: Design specs, requirements
├── Output: Working code
└── Validation: Code compiles, basic tests pass

PHASE 3: ANALYSIS
├── Command: /analyze, /explain
├── Persona: Appropriate domain expert
├── Input: Implemented code
├── Output: Analysis report, improvements
└── Validation: All issues documented

PHASE 4: QUALITY ASSURANCE
├── Command: /review, /audit, /test, /security
├── Persona: QA, Security as needed
├── Input: Code to review
├── Output: Review findings, security audit
└── Validation: All critical issues resolved

PHASE 5: DOCUMENTATION
├── Command: /document
├── Persona: Technical Writer (implicit)
├── Input: Finalized code
├── Output: Documentation, API docs
└── Validation: Docs complete and accurate

MODE SELECTION:
- Exploration: --mode-brainstorming
- Production: --mode-efficient
- Research: --mode-deep-research
```

### Y. Prompt Engineering

**Command Invocation Pattern**:
```markdown
/[command] --persona-[persona] --mode-[mode]

Context: [What you're working on]
Goal: [What you want to achieve]
Constraints: [Any limitations]
```

**Evidence-Based Request**:
```markdown
/analyze --persona-security

Before suggesting fixes:
1. Look up official documentation for [framework]
2. Find CVE database entries if applicable
3. Cite specific sources for recommendations
```

**Persona Switching Pattern**:
```markdown
Phase 1: /scaffold --persona-architect
[Review output]

Phase 2: /implement --persona-backend
[Review output]

Phase 3: /security --persona-security
[Review findings]
```

### Z. Guardrails and Quality

**Execution Guardrails**:
1. **Evidence Requirement**: RULES.md enforces documentation lookup
2. **Persona Appropriateness**: Match persona to task type
3. **Mode Selection**: Use efficient mode for large projects
4. **MCP Fallback**: Commands work without MCPs
5. **Output Validation**: Review all suggestions before accepting

**Quality Metrics**:
| Metric | Target | Measurement |
|--------|--------|-------------|
| Command Coverage | 100% | All lifecycle phases have commands |
| Evidence Citations | Required | All suggestions cite sources |
| Token Efficiency | 30-70% | Reduction vs baseline |
| Persona Match | Correct | Persona matches task domain |
| Mode Appropriate | Matched | Mode matches project size/phase |

**Anti-Patterns to Avoid**:
1. **Persona Overload**: Using too many personas in one session
2. **Mode Mismatch**: Using brainstorming mode for production code
3. **Evidence Bypass**: Accepting suggestions without source verification
4. **MCP Dependency**: Building workflows that require MCPs
5. **Command Chaining**: Too many commands without review
6. **Ignoring RULES.md**: Disabling evidence-based methodology

---

## Sources and References

1. **Primary Repository**: https://github.com/SuperClaude-Org/SuperClaude_Framework
2. **Official Website**: https://superclaude.org/
3. **Alternative Repository**: https://github.com/NomenAK/SuperClaude
4. **ClaudeLog Documentation**: https://claudelog.com/claude-code-mcps/super-claude/
5. **2025 Developer Guide**: https://medianeth.dev/blog/claude-code-frameworks-subagents-2025

---

*Analysis generated via research-framework-analyzer skill with confirmed invocation*


---

## Navigation

- [← Back to All Frameworks](index.md)
- [Comparison with similar frameworks](../comparisons/.md)
- [Full Synthesis](../synthesis.md)