---
title: RIPER-5
layout: default
parent: Frameworks
---

# RIPER-5

<div class="framework-meta">
<strong>Version:</strong> 2025.11 |
<strong>Repository:</strong> <a href="https://github.com/NeekChaw/RIPER-5">GitHub</a> |
<strong>License:</strong> MIT
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: prompt-based</span>
<span class="badge badge-exec">exec: sequential</span>
<span class="badge badge-function">function: dev-methodology</span>
<span class="badge badge-ecosystem">ecosystem: agnostic</span>
<span class="badge badge-scope">scope: project-level</span>
<span class="badge badge-integration">integration: drop-in</span>
<span class="badge badge-user">user: solo-dev</span>
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
<td>4.2/5.0 ⭐⭐⭐⭐☆</td>
<td><strong>Overall</strong></td>
<td>72/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>4.5/5.0</td>
<td>Reliability</td>
<td>65</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>4.0/5.0</td>
<td>Observability</td>
<td>60</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>4.0/5.0</td>
<td>Security</td>
<td>75</td>
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
<td>75</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Behavioral constraint protocol (5 phases)</li>
<li>Permission-based enforcement per mode</li>
<li>100% fidelity execution requirement</li>
<li>Branch-aware memory bank</li>
<li>Multiple variants (Original, Sigma, Claude Code)</li>
</ul>

## Best For

<ul class="compact-list">
<li>Complex multi-step feature development</li>
<li>Critical code refactoring in production</li>
<li>High-liability projects (fintech, healthcare)</li>
<li>Teams learning disciplined AI development</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Not for quick prototypes (<2 weeks)</li>
<li>Not for simple bug fixes (<20 lines)</li>
<li>Overhead for exploratory coding</li>
</ul>

---

## Full Analysis

# RIPER-5 Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-research:framework-analyzer")
> - Template Version: 1.1
> - Category: methodology

## Research Metadata

| Field | Value |
|-------|-------|
| **Framework** | RIPER-5 |
| **Version** | Multiple implementations |
| **Repository** | [NeekChaw/RIPER-5](https://github.com/NeekChaw/RIPER-5) (Community) |
| **Claude Code Repo** | [tony/claude-code-riper-5](https://github.com/tony/claude-code-riper-5) |
| **Category** | Methodology |
| **Stars** | 1,900+ (community), 39 (claude-code) |
| **Forks** | 276 |
| **License** | MIT |
| **Analysis Date** | November 28, 2025 |
| **Template Version** | 1.1 |
| **SOLID Score** | 4.2/5.0 |
| **Production Score** | 72/100 |
| **Complexity** | LIGHTWEIGHT |

---

## 1. Overview & Context

RIPER-5 is a behavioral constraint protocol designed to control AI assistant behavior during software development through five sequential phases: **R**esearch, **I**nnovate, **P**lan, **E**xecute, and **R**eview. Unlike project management frameworks, RIPER-5 focuses on constraining AI behavior to prevent unauthorized modifications and premature implementations.

### Core Innovation

The framework's fundamental insight is that AI assistants tend to be "overeager" and often implement changes without explicit request. RIPER-5 addresses this through **process discipline via technical architecture** - using explicit mode declarations, permission matrices, and mandatory transition rules.

### Key Differentiators

1. **Behavioral Constraint Focus**: Controls what AI can and cannot do per phase
2. **Permission-Based Enforcement**: Each mode has explicit read/write/execute permissions
3. **Zero Tolerance for Deviation**: "100% fidelity" execution requirement
4. **Branch-Aware Memory Bank**: Context persistence by git branch
5. **Multiple Variants**: Original, Sigma (compact), Claude Code adaptations

### Target Use Cases

**Optimal For:**
- Complex multi-step feature development
- Critical code refactoring in production systems
- High-liability projects (fintech, healthcare)
- Teams learning disciplined AI-assisted development

**Not Recommended For:**
- Quick prototypes (<2 weeks)
- Simple bug fixes (<20 lines)
- Exploratory/experimental coding
- Rapid iteration environments

**Sources:** GitHub repositories, Cursor Community Forum

---

## 2. Architecture & Design

### 2.1 Component Architecture

RIPER-5 operates as a behavioral protocol rather than software:

```
RIPER-5/
├── Phase Definitions/          # Five core phases
│   ├── RESEARCH mode           # Read-only investigation
│   ├── INNOVATE mode           # Solution brainstorming
│   ├── PLAN mode               # Detailed planning
│   ├── EXECUTE mode            # Implementation
│   └── REVIEW mode             # Verification
├── Permission Matrix/          # Phase-specific capabilities
├── Memory Bank/                # Context persistence
│   ├── main/
│   │   ├── plans/
│   │   ├── reviews/
│   │   └── sessions/
│   └── [feature-branch]/
└── Transition Rules/           # Phase progression logic
```

### 2.2 Data Flow

```
User Request → Phase Detection → Permission Check → Action Execution
     │
     ▼
Memory Bank ← Session Logging → Branch-Specific Storage
     │
     ▼
Next Phase Transition (explicit user command only)
```

### 2.3 Integration Points

**Phase Permissions:**

| Phase | Read | Write | Execute | Key Actions |
|-------|------|-------|---------|-------------|
| RESEARCH | ✅ | ❌ | ❌ | Analyze, investigate, understand |
| INNOVATE | ✅ | ❌ | ❌ | Brainstorm, suggest, explore |
| PLAN | ✅ | ✅ Plans | ❌ | Detail steps, document approach |
| EXECUTE | ✅ | ✅ Code | ✅ | Implement exactly as planned |
| REVIEW | ✅ | ❌ | ❌ | Verify, test, validate |

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

**Phases:** RESEARCH → INNOVATE → PLAN

- RESEARCH: Deep codebase analysis without modification
- INNOVATE: Solution exploration and alternatives
- PLAN: Detailed implementation specifications

**Automation:** Mode transitions require explicit user commands.

### 3.2 Execution Phase

**Phase:** EXECUTE

- Only phase with write and execute permissions
- "100% fidelity" requirement - implement exactly as planned
- No deviations, improvements, or refactoring allowed

### 3.3 Review Phase

**Phase:** REVIEW

- Read-only verification
- Compare implementation against plan
- Report discrepancies without fixing

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle

**Score: 4.5/5**

Each phase has one clear responsibility:
- RESEARCH: Understand only
- INNOVATE: Suggest only
- PLAN: Document only
- EXECUTE: Implement only
- REVIEW: Verify only

### 4.2 Open-Closed Principle

**Score: 4.5/5**

- Protocol is closed for modification (core phases fixed)
- Open for extension (variants like Sigma, Claude Code adaptations)
- Memory Bank system extensible

### 4.3 Liskov Substitution Principle

**Score: 4.0/5**

- Phase implementations substitutable within constraints
- Sigma variant maintains behavioral compatibility
- Some variants break strict substitution

### 4.4 Interface Segregation Principle

**Score: 4.0/5**

- Minimal interface per phase (single permission set)
- No bloated capabilities
- Clean phase separation

### 4.5 Dependency Inversion Principle

**Score: 4.0/5**

- Depends on abstractions (phase definitions)
- Memory Bank abstraction layer
- Implementation-agnostic protocol

**Overall SOLID Score:** 4.2/5.0

**Justification:** RIPER-5 demonstrates excellent adherence to SOLID principles through its clean phase separation and permission-based architecture. Each phase has a single, well-defined responsibility with explicit boundaries. The protocol's simplicity naturally enforces good design principles. Minor weaknesses emerge in variant compatibility (LSP) and some concrete dependencies in Memory Bank implementation.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**Score: 65/100**

- Protocol itself is simple and reliable
- No runtime dependencies
- User compliance required for enforcement
- Multiple variants create inconsistency

### 5.2 Observability

**Score: 60/100**

- Memory Bank provides session logging
- No structured telemetry
- Manual review of phase transitions
- Limited audit trail

### 5.3 Security

**Score: 75/100**

- Permission-based access control
- Read-only by default (most phases)
- No external network dependencies
- Relies on AI compliance

### 5.4 Performance

**Score: 85/100**

- Zero runtime overhead (protocol-only)
- Minimal token consumption
- No external API calls
- Lightweight Memory Bank

### 5.5 Maintainability

**Score: 75/100**

- Simple protocol easy to maintain
- Multiple variants create fragmentation
- Community-driven updates
- Clear documentation

**Overall Production Score:** 72/100

---

## 6. Best Practices & Patterns

### Permission Matrix Pattern

RIPER-5's core innovation - explicit capability boundaries:

```yaml
RESEARCH:
  allowed: [read_code, analyze, investigate, ask_questions]
  forbidden: [modify_code, suggest_changes, execute]

EXECUTE:
  allowed: [read_code, write_code, run_commands]
  forbidden: [deviate_from_plan, refactor, improve]
```

### Mode Transition Pattern

Explicit user commands required:
```
User: "Switch to EXECUTE mode"
AI: [Acknowledges mode change, lists new permissions]
```

### Memory Bank Pattern

Branch-aware context persistence:
```
.claude/memory-bank/
├── main/          # Main branch context
├── feature-x/     # Feature branch context
└── sessions/      # Session transcripts
```

---

## 7. Limitations & Trade-offs

### Critical Limitations

**1. Enforcement Gap**
- Protocol relies on AI voluntary compliance
- No technical enforcement mechanism
- User must monitor for violations

**2. Rigidity vs Flexibility Trade-off**
- "100% fidelity" prevents beneficial adaptations
- No room for execution-time improvements
- Plans must be perfect before execution

**3. Variant Fragmentation**
- Multiple incompatible implementations
- No canonical version
- Community confusion

### Operational Limitations

**4. Overhead for Simple Tasks**
- Five-phase process overkill for bug fixes
- No "quick mode" for trivial changes

**5. No Multi-Agent Support**
- Single-assistant protocol only
- No orchestration capabilities

---

## 8. Community & Ecosystem

### Community Metrics

| Metric | Value |
|--------|-------|
| Community Stars | 1,900+ |
| Claude Code Stars | 39 |
| Forks | 276 |
| Origin | Cursor Forum (March 2025) |
| Creator | robotlovehuman (Anonymous) |

### Sentiment Distribution

- 80% Positive (fixes AI overreach)
- 15% Neutral (useful but rigid)
- 5% Negative (too restrictive)

### Notable Variants

1. **Original**: Full forum post specification
2. **Sigma**: Ultra-compact version (fits context window)
3. **Claude Code**: Tony Narlock's adaptation
4. **CursorRIPER**: johnpeterman72's implementation

---

## 9. Innovation & Differentiation

### Unique Contributions

**1. Behavioral Constraint Architecture**
First framework to focus on constraining AI behavior rather than organizing tasks.

**2. Permission Matrix Concept**
Explicit read/write/execute permissions per phase - novel approach to AI safety.

**3. Zero-Deviation Philosophy**
"100% fidelity" execution principle prevents scope creep.

**4. Branch-Aware Context**
Memory Bank organized by git branch - enables parallel feature development.

### Competitive Position

| Feature | RIPER-5 | Competitors |
|---------|---------|-------------|
| Behavioral Constraint | Primary focus | Secondary |
| Overhead | Minimal | Often heavy |
| Learning Curve | Low | Moderate |
| Enforcement | Voluntary | Varies |

---

## 10. References & Sources

1. **Cursor Forum Original Post**
   - https://forum.cursor.com/t/i-created-an-amazing-mode-called-riper-5-mode-fixes-claude-3-7-drastically/65516

2. **Community Repository**
   - https://github.com/NeekChaw/RIPER-5

3. **Claude Code Implementation**
   - https://github.com/tony/claude-code-riper-5

4. **CursorRIPER Variants**
   - https://github.com/johnpeterman72/CursorRIPER

5. **Forum Discussion Analysis**
   - 8+ pages of community feedback

---

## 11. Error Handling Patterns

### 11.1 Error Detection

**Phase Violation Detection:**
- Monitor for unauthorized modifications in read-only phases
- Flag execution without prior planning
- Detect scope deviations

### 11.2 Error Recovery

**Rollback Strategy:**
```
If execution deviates from plan:
1. Stop execution immediately
2. Return to REVIEW mode
3. Document deviation
4. Revise plan or rollback changes
```

### 11.3 Error Reporting

**Memory Bank Logging:**
- Session transcripts capture all actions
- Phase transitions logged
- Violations documented for review

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

**Minimal Protocol Overhead:**
- Core protocol fits in ~2k tokens
- Sigma variant: ~500 tokens
- No large context files required

**Phase-Specific Loading:**
- Only current phase permissions loaded
- Memory Bank lazy-loaded as needed

### 12.2 Context Management

**Branch Isolation:**
- Separate context per branch
- No cross-branch pollution
- Clean session boundaries

**Comparison:**

| Aspect | RIPER-5 | Heavy Frameworks |
|--------|---------|------------------|
| Protocol Size | ~2k tokens | 10-50k tokens |
| Runtime Overhead | Zero | Significant |
| Context Usage | Minimal | Often maxes out |

---

## X. Process Discipline Mechanisms

### Phase Enforcement Architecture

RIPER-5's discipline comes from explicit constraints:

**Hard Boundaries:**
- No code modifications in RESEARCH/INNOVATE/REVIEW
- No deviations in EXECUTE
- Explicit mode transitions only

**Compliance Monitoring:**
- User responsible for enforcement
- AI self-reports phase status
- Memory Bank audit trail

### Discipline Patterns

1. **Mode Declaration**: AI states current mode before actions
2. **Permission Check**: AI verifies action is allowed
3. **Transition Protocol**: Explicit user command required
4. **Fidelity Requirement**: Exact plan execution

---

## Y. Learning Loop Architecture

### Y.1 Knowledge Capture

**Memory Bank System:**
- Plans stored for reference
- Reviews captured for patterns
- Sessions logged for continuity

### Y.2 Knowledge Application

**Branch-Aware Context:**
- Previous plans inform current work
- Review insights guide improvements
- Session history provides continuity

### Y.3 Knowledge Evolution

**Iterative Refinement:**
- REVIEW phase identifies gaps
- Next cycle incorporates learnings
- Plans improve over iterations

---

## Z. Progressive Disclosure Design

### Complexity Tiers

**Tier 1: Essential (Sigma)**
- 5 phases, minimal rules
- ~500 tokens
- Quick adoption

**Tier 2: Standard**
- Full permission matrix
- Memory Bank integration
- ~2k tokens

**Tier 3: Advanced**
- Multiple variants
- Custom workflows
- Branch strategies

### User Journey

1. **Beginner**: Use Sigma variant, learn phases
2. **Intermediate**: Full protocol with Memory Bank
3. **Advanced**: Custom adaptations, variant selection

---

## Conclusion

RIPER-5 represents a unique approach to AI-assisted development methodology by focusing on behavioral constraints rather than task organization. Its simplicity (LIGHTWEIGHT complexity rating) makes it accessible while the strict phase discipline addresses real concerns about AI overreach.

**Key Strengths:**
- Minimal overhead (zero runtime dependencies)
- Clear phase boundaries with explicit permissions
- Effective at preventing unauthorized modifications
- Multiple variants for different needs

**Key Challenges:**
- Relies on voluntary AI compliance
- Rigid for simple tasks
- Variant fragmentation creates confusion
- No technical enforcement mechanism

**Comparison to BMAD Method:**

| Aspect | RIPER-5 | BMAD Method |
|--------|---------|-------------|
| Focus | Behavioral constraint | Full methodology |
| Complexity | LIGHTWEIGHT | HEAVY |
| Overhead | Minimal | Significant |
| SOLID Score | 4.2/5.0 | 4.3/5.0 |
| Production Score | 72/100 | 87/100 |

**Bottom Line:** RIPER-5 excels for developers seeking lightweight behavioral discipline without heavy methodology overhead. Best for individual developers or small teams wanting to prevent AI overreach while maintaining agility.


---

<footer class="generation-meta">
<small>
Generated: 2025-12-01 22:56 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/riper-5">Source Data</a>
</small>
</footer>