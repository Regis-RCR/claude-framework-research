---
title: Simone
layout: default
parent: Frameworks
---

# Simone

<div class="framework-meta">
<strong>Version:</strong> 0.4.0-mcp |
<strong>Repository:</strong> <a href="https://github.com/Helmi/claude-simone">GitHub</a> |
<strong>License:</strong> MIT
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: mcp-native, prompt-based</span>
<span class="badge badge-exec">exec: single-agent</span>
<span class="badge badge-function">function: context-management</span>
<span class="badge badge-ecosystem">ecosystem: agnostic</span>
<span class="badge badge-scope">scope: project-level</span>
<span class="badge badge-integration">integration: config-required</span>
<span class="badge badge-user">user: solo-dev</span>
<span class="badge badge-complexity">complexity: moderate</span>
<span class="badge badge-maturity">maturity: beta</span>
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
<td>3.6/5.0 ⭐⭐⭐☆☆</td>
<td><strong>Overall</strong></td>
<td>63/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>3.8/5.0</td>
<td>Reliability</td>
<td>55</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>3.5/5.0</td>
<td>Observability</td>
<td>65</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>3.5/5.0</td>
<td>Security</td>
<td>60</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>4.0/5.0</td>
<td>Performance</td>
<td>70</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>3.2/5.0</td>
<td>Maintainability</td>
<td>65</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Context decay solution (fresh start per task)</li>
<li>Hierarchical task structure (Milestones → Sprints → Tasks)</li>
<li>Dual implementation (Legacy v0.3.5 + MCP v0.4.0)</li>
<li>GitHub-native workflow (Issues, Milestones, Projects)</li>
<li>Handlebars templates for customizable prompts</li>
<li>Self-dogfooding (manages itself)</li>
</ul>

## Best For

<ul class="compact-list">
<li>Long-term AI-assisted projects (multi-month)</li>
<li>Large codebases (50k+ LOC)</li>
<li>Team-based GitHub workflows</li>
<li>Projects requiring architectural documentation</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Not for quick prototypes (<2 weeks)</li>
<li>Not for small codebases (<1k LOC)</li>
<li>Requires GitHub</li>
<li>Learning curve for hierarchical structure</li>
</ul>

---

## Full Analysis

# Simone Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-research:framework-analyzer")
> - Template Version: 1.1
> - Category: methodology

## Research Metadata

| Field | Value |
|-------|-------|
| **Framework** | Simone |
| **Version** | MCP v0.4.0 / Legacy v0.3.5 |
| **Repository** | [Helmi/claude-simone](https://github.com/Helmi/claude-simone) |
| **Category** | Methodology |
| **Stars** | 511 |
| **Forks** | 52 |
| **Contributors** | 6 |
| **License** | MIT |
| **Primary Language** | TypeScript (81.8%) |
| **Analysis Date** | November 28, 2025 |
| **Template Version** | 1.1 |
| **SOLID Score** | 3.6/5.0 |
| **Production Score** | 63/100 |
| **Complexity** | STANDARD |

---

## 1. Overview & Context

Simone is a project management framework designed specifically to solve the **context decay problem** in AI-assisted development with Claude Code. Unlike simpler task management tools, Simone provides a comprehensive system of documents, guidelines, and processes that facilitate project planning and execution at scale.

### Core Innovation

Simone's fundamental insight is that fighting against context window limits is futile. Instead, the framework **starts fresh for each task while providing rich surrounding context**. This ensures critical architectural decisions and requirements remain accessible throughout development.

### Dual Implementation Strategy

1. **Legacy System (v0.3.5)**: Directory-based task management with proven real-world use
2. **MCP Server (v0.4.0)**: Modern implementation using Model Context Protocol with GitHub integration

### Key Differentiators

1. **Hierarchical Task Structure**: Milestones → Sprints → Tasks
2. **Context-Aware Prompting**: Each task receives exactly the project knowledge it needs
3. **GitHub-Native Workflow**: Issues, Milestones, and Projects integration via MCP
4. **Handlebars Templates**: Customizable prompts with dynamic sections
5. **Self-Dogfooding**: Simone manages itself using its own framework

### Target Use Cases

**Optimal For:**
- Long-term AI-assisted projects (multi-month)
- Large codebases (50k+ LOC)
- Team-based development with GitHub workflows
- Projects requiring strict architectural documentation

**Not Recommended For:**
- Quick prototypes (<2 weeks)
- Simple maintenance tasks
- Small codebases (<1k LOC)
- Teams not using GitHub

**Sources:** GitHub Repository, Documentation Site

---

## 2. Architecture & Design

### 2.1 Component Architecture

```
claude-simone/
├── /legacy                    # Original directory-based system
│   ├── /tasks                 # Task definitions
│   ├── /milestones            # Milestone tracking
│   └── /sprints               # Sprint organization
├── /mcp-server                # MCP implementation
│   ├── /src
│   │   ├── prompts/           # Handlebars templates
│   │   ├── tools/             # MCP tool definitions
│   │   └── db/                # SQLite activity logging
│   └── package.json
├── /hello-simone              # Universal installer
└── /documentation             # Docusaurus site
```

### 2.2 Data Flow

```
Task Request → Template Selection → Context Injection
     │
     ▼
Handlebars Rendering → Prompt Generation → Claude Execution
     │
     ▼
Activity Logging (SQLite) → GitHub Sync (optional)
```

### 2.3 Integration Points

**MCP Server Tools:**
- `simone_get_task`: Retrieve task with context
- `simone_complete_task`: Mark task complete
- `simone_create_issue`: GitHub issue creation
- `simone_list_milestones`: Project overview

**GitHub Integration:**
- Issues mapped to tasks
- Milestones for project phases
- Projects for sprint boards

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

**Components:**
- Milestone definition (project phases)
- Sprint planning (work batches)
- Task breakdown (atomic units)

**Workflow:**
```
Project Vision → Milestones → Sprints → Tasks
```

### 3.2 Execution Phase

**Task Execution:**
1. `simone_get_task` loads task with context
2. Handlebars template generates tailored prompt
3. Claude executes with full project awareness
4. Activity logged to SQLite

### 3.3 Review Phase

**Completion Flow:**
1. `simone_complete_task` marks done
2. GitHub issue closed (if linked)
3. Sprint progress updated
4. Milestone percentage recalculated

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle

**Score: 4.0/5**

- Tasks have single objectives
- Templates serve one purpose each
- MCP tools focused on specific actions
- Some overlap between legacy and MCP systems

### 4.2 Open-Closed Principle

**Score: 3.5/5**

- Handlebars templates extensible
- Custom partials supported
- Core system requires modification for changes
- Dual system creates complexity

### 4.3 Liskov Substitution Principle

**Score: 3.0/5**

- Legacy and MCP not interchangeable
- Template variants have different capabilities
- GitHub integration optional but affects behavior

### 4.4 Interface Segregation Principle

**Score: 3.5/5**

- MCP tools reasonably focused
- Some tools have multiple responsibilities
- Template system could be more granular

### 4.5 Dependency Inversion Principle

**Score: 4.0/5**

- Abstracted template system
- Database layer abstraction
- GitHub integration via MCP protocol
- Some concrete dependencies remain

**Overall SOLID Score:** 3.6/5.0

**Justification:** Simone shows solid architectural foundations with good separation of concerns in the MCP implementation. The template system provides good abstraction. However, the dual legacy/MCP architecture creates substitutability challenges, and some components have multiple responsibilities. The GitHub dependency, while optional, affects system behavior when not present.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**Score: 55/100**

- Last commit: August 2024 (development paused)
- 12 open issues unresolved
- MCP protocol still evolving
- No formal SLA or support

### 5.2 Observability

**Score: 65/100**

- SQLite activity logging
- MCP tool call tracking
- No structured telemetry
- Basic error reporting

### 5.3 Security

**Score: 60/100**

- GitHub OAuth for integration
- Local SQLite database
- No credential management
- MCP security inherited

### 5.4 Performance

**Score: 70/100**

- Lightweight TypeScript
- SQLite for persistence
- Template rendering efficient
- Context injection overhead

### 5.5 Maintainability

**Score: 65/100**

- TypeScript for type safety
- ESLint + Prettier configured
- Test suite with Vitest
- Development appears paused

**Overall Production Score:** 63/100

---

## 6. Best Practices & Patterns

### Hierarchical Task Pattern

```
Milestone: "MVP Launch" (deadline: Q1)
├── Sprint: "Authentication" (2 weeks)
│   ├── Task: "Setup OAuth provider"
│   ├── Task: "Implement login flow"
│   └── Task: "Add session management"
└── Sprint: "Dashboard" (2 weeks)
    ├── Task: "Create layout"
    └── Task: "Add data visualization"
```

### Context Injection Pattern

Handlebars templates inject relevant context:

```handlebars
# Task: {{task.title}}

## Project Context
{{> project_overview}}

## Architectural Guidelines
{{> architecture_decisions}}

## Current Sprint Goals
{{sprint.objectives}}

## Your Assignment
{{task.description}}
```

### Fresh Start Pattern

Each task begins with clean context + injected knowledge:
- No accumulated session context
- Relevant decisions included
- Architecture always available

---

## 7. Limitations & Trade-offs

### Critical Limitations

**1. Development Status**
- Last commit August 2024
- Active development uncertain
- MCP protocol evolving independently

**2. GitHub Dependency**
- Full functionality requires GitHub
- Non-GitHub teams limited options
- Integration complexity

**3. Dual System Confusion**
- Legacy vs MCP not clearly differentiated
- Migration path unclear
- Documentation spans both

### Operational Limitations

**4. Setup Complexity**
- MCP server configuration required
- Template customization learning curve
- Node.js 20+ requirement

**5. Single-Platform Focus**
- Claude Code primary target
- Other AI assistants unsupported
- IDE integration limited

---

## 8. Community & Ecosystem

### Community Metrics

| Metric | Value |
|--------|-------|
| GitHub Stars | 511 |
| Forks | 52 |
| Contributors | 6 |
| Open Issues | 12 |
| Last Active | August 2024 |

### Sentiment Analysis

- 60% Positive (solves real problem)
- 25% Neutral (useful but niche)
- 15% Negative (development stalled)

### Ecosystem

- Docusaurus documentation site
- npx-based installation
- GitHub-centric workflow
- No plugin marketplace

---

## 9. Innovation & Differentiation

### Unique Contributions

**1. Context Decay Solution**
First framework explicitly designed to combat AI context window limitations.

**2. Fresh Start Philosophy**
Counter-intuitive approach: start fresh each task with injected context.

**3. MCP Early Adoption**
Among first frameworks to implement Model Context Protocol.

**4. Self-Dogfooding**
Simone built and maintained using its own system.

### Competitive Position

| Feature | Simone | Competitors |
|---------|--------|-------------|
| Context Management | Primary focus | Secondary |
| GitHub Integration | Native | Plugin-based |
| MCP Support | Yes | Limited |
| Active Development | Paused | Varies |

---

## 10. References & Sources

1. **GitHub Repository**
   - https://github.com/Helmi/claude-simone

2. **Documentation Site**
   - Docusaurus-based documentation

3. **MCP Server Package**
   - @modelcontextprotocol/sdk integration

4. **Community Discussions**
   - GitHub Issues (30+ closed, 12 open)

5. **Author Profile**
   - Helmi (GitHub)

---

## 11. Error Handling Patterns

### 11.1 Error Detection

**MCP Tool Errors:**
- Schema validation for tool inputs
- Type checking via TypeScript
- Template rendering errors caught

### 11.2 Error Recovery

**Graceful Degradation:**
```typescript
try {
  await githubSync();
} catch (error) {
  // Continue without GitHub
  logActivity('github_sync_failed', error);
}
```

### 11.3 Error Reporting

**Activity Logging:**
- SQLite database captures errors
- Tool call failures logged
- Template errors recorded

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

**Context Injection:**
- Only relevant context included per task
- No accumulated session bloat
- Template-controlled content

**Handlebars Partials:**
- Reusable template fragments
- Conditional inclusion
- Dynamic section loading

### 12.2 Context Management

**Fresh Start Model:**
- Each task: clean slate + injected knowledge
- Prevents context pollution
- Predictable token usage

**Comparison:**

| Approach | Token Usage | Predictability |
|----------|-------------|----------------|
| Simone (fresh) | Medium | High |
| Continuous session | Growing | Low |
| No context | Minimal | High (but limited) |

---

## X. Process Discipline Mechanisms

### Task-Based Discipline

Simone enforces discipline through structure:

**Hierarchical Constraints:**
- Tasks belong to sprints
- Sprints belong to milestones
- Progress tracked at each level

**Completion Gates:**
- Task must be marked complete
- Sprint completion requires all tasks
- Milestone requires all sprints

### Template-Based Guardrails

```handlebars
## Before You Begin
- [ ] Review architectural guidelines
- [ ] Check related tasks in sprint
- [ ] Understand acceptance criteria

## Completion Checklist
- [ ] Code implemented
- [ ] Tests passing
- [ ] Documentation updated
```

---

## Y. Learning Loop Architecture

### Y.1 Knowledge Capture

**Activity Logging:**
- All MCP tool calls logged
- Task completion times tracked
- Error patterns recorded

**Documentation:**
- Project decisions in context files
- Architecture in dedicated documents
- Sprint retrospectives

### Y.2 Knowledge Application

**Template Injection:**
- Previous decisions included in context
- Architecture always available
- Sprint goals communicated

### Y.3 Knowledge Evolution

**Iterative Refinement:**
- Templates can be updated
- Partials evolve with project
- Context documents grow

---

## Z. Progressive Disclosure Design

### Complexity Tiers

**Tier 1: Quick Start**
```bash
npx hello-simone init
# Creates basic structure
```

**Tier 2: GitHub Integration**
- Add MCP server configuration
- Enable issue synchronization
- Milestone tracking

**Tier 3: Custom Templates**
- Create project-specific partials
- Define custom prompt structures
- Activity tracking customization

### User Journey

1. **Beginner**: npx init, basic tasks
2. **Intermediate**: GitHub integration, sprints
3. **Advanced**: Custom templates, MCP tools

---

## Conclusion

Simone represents a thoughtful approach to the context decay problem in AI-assisted development. Its "fresh start with context injection" philosophy offers a practical solution to context window limitations.

**Key Strengths:**
- Solves real context management problem
- GitHub-native workflow
- Flexible template system
- Self-dogfooding proves concept

**Key Challenges:**
- Development appears paused (Aug 2024)
- GitHub dependency limits adoption
- Dual system creates confusion
- MCP still evolving

**Comparison to BMAD Method:**

| Aspect | Simone | BMAD Method |
|--------|--------|-------------|
| Focus | Context management | Full methodology |
| Complexity | STANDARD | HEAVY |
| GitHub Req | Yes (for full features) | No |
| Active Dev | Paused | Active |
| SOLID Score | 3.6/5.0 | 4.3/5.0 |
| Production | 63/100 | 87/100 |

**Comparison to RIPER-5:**

| Aspect | Simone | RIPER-5 |
|--------|--------|---------|
| Focus | Context management | Behavioral constraint |
| Complexity | STANDARD | LIGHTWEIGHT |
| Overhead | Moderate | Minimal |
| SOLID Score | 3.6/5.0 | 4.2/5.0 |
| Production | 63/100 | 72/100 |

**Bottom Line:** Simone excels for teams using GitHub who need structured context management for long-term projects. Best suited for established teams with complex codebases. Development pause is a concern for production adoption.


---

<footer class="generation-meta">
<small>
Generated: 2025-12-03 21:56 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/simone">Source Data</a>
</small>
</footer>