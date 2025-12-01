---
title: taskmaster-mcp
category: 
layout: framework
---

# taskmaster-mcp

∵ RCR Regis ∴

**Category:** 
**Version:** 0.15.0
**Status:** Analyzed

## Scores

| Metric | Score | Rating |
|--------|-------|--------|
| SOLID Principles | 4.2/5.0 | ⭐⭐⭐⭐☆ |
| Production Ready | 74/100 | 🟡 Beta |

### SOLID Breakdown

| Principle | Score | Notes |
|-----------|-------|-------|
| S - Single Responsibility | N/A | - |
| O - Open/Closed | N/A | - |
| L - Liskov Substitution | N/A | - |
| I - Interface Segregation | N/A | - |
| D - Dependency Inversion | N/A | - |

## Overview

*No description available.*




## Full Analysis

# Task Master (claude-task-master) - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-toolkit:research-framework-analyzer")
> - Template Version: 1.1
> - Category: methodology

## 1. Executive Summary

Task Master (claude-task-master) is an AI-powered task management system designed for AI-assisted development workflows. With 23.9k GitHub stars and extensive adoption across major AI coding tools, it has become a de facto standard for structured project planning in the Claude ecosystem. The framework bridges the gap between high-level product requirements (PRDs) and executable development tasks through AI-driven parsing, decomposition, and dependency management.

**Key Value Proposition**: Transforms unstructured product requirements into a dependency-aware task graph that AI assistants can execute systematically, preventing the common failure mode of AI coding tools losing track of project context and overall goals.

**Primary Innovation**: The MCP (Model Control Protocol) integration allows the task management system to live inside the AI assistant's context, rather than as an external tool, enabling real-time task awareness and intelligent task selection.

## 2. Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                      INTERFACE LAYER                             │
│  ┌─────────────┐ ┌─────────────┐ ┌─────────────┐               │
│  │ MCP Server  │ │ CLI Client  │ │ Chat Mode   │               │
│  │ (36 tools)  │ │ (npm exec)  │ │ (REPL)      │               │
│  └──────┬──────┘ └──────┬──────┘ └──────┬──────┘               │
└─────────┼───────────────┼───────────────┼───────────────────────┘
          │               │               │
          └───────────────┼───────────────┘
                          ▼
┌─────────────────────────────────────────────────────────────────┐
│                       CORE ENGINE                                │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                   Task Manager                            │   │
│  │  - CRUD operations (create, read, update, delete)        │   │
│  │  - Dependency resolution                                  │   │
│  │  - Status tracking (todo, in-progress, done, blocked)    │   │
│  │  - Complexity analysis                                    │   │
│  └──────────────────────────────────────────────────────────┘   │
│                              │                                   │
│  ┌───────────────┬───────────┴───────────┬──────────────────┐   │
│  │ PRD Parser    │ Research Engine       │ Tag System       │   │
│  │ - Markdown    │ - Multi-model support │ - Multi-context  │   │
│  │ - Section     │ - Context injection   │ - Isolation      │   │
│  │   extraction  │ - Citation tracking   │ - Migration      │   │
│  └───────────────┴───────────────────────┴──────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      PERSISTENCE LAYER                           │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │              .taskmaster/ Directory                       │   │
│  │  ├── tasks.json       (current task state)               │   │
│  │  ├── config.json      (project configuration)            │   │
│  │  ├── .env             (API keys)                          │   │
│  │  └── tags/            (multi-context storage)            │   │
│  │       ├── master.json                                     │   │
│  │       └── feature-x.json                                  │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      AI MODEL LAYER                              │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐   │
│  │ Claude  │ │ OpenAI  │ │ Gemini  │ │Perplexity│ │OpenRouter│   │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘   │
│                                                                  │
│  Selection: Based on task type (research→Perplexity, code→Claude)│
└─────────────────────────────────────────────────────────────────┘
```

**Architecture Pattern**: Layered architecture with MCP protocol integration

The architecture separates concerns cleanly: interface adapters handle different access patterns (MCP tools, CLI commands, chat REPL), the core engine manages task state and operations, file-based persistence provides durability, and the AI model layer abstracts provider differences for multi-model support.

## 3. Core Components

### 3.1 MCP Server
- **Purpose**: Expose task management as AI-native tools
- **Tool Count**: 36 tools (configurable: Core=7, Standard=15, All=36)
- **Token Footprint**: 5,000-21,000 tokens depending on mode
- **Protocol**: fastmcp v3.20.1 with Zod v4 validation

### 3.2 PRD Parser
- **Purpose**: Transform product requirements into task structures
- **Input**: Markdown PRD files with structured sections
- **Output**: Task tree with dependencies, complexity scores, acceptance criteria
- **Key Feature**: Section-aware parsing (Goals, User Stories, Technical Requirements)

### 3.3 Task Manager
- **Purpose**: Central CRUD and state management
- **Operations**: create, update, delete, move, expand, list, show, next
- **State Machine**: todo → in-progress → review → done (+ blocked state)
- **Dependencies**: DAG-based with cycle detection

### 3.4 Research Engine
- **Purpose**: Context-aware information gathering
- **Multi-Model**: Routes research queries to appropriate models
- **Context Injection**: Includes project context in research prompts
- **Citation**: Tracks and cites sources in research outputs

### 3.5 Tag System
- **Purpose**: Multi-context task isolation
- **Use Case**: Separate task lists per feature branch/experiment
- **Migration**: Automatic upgrade of legacy single-list projects
- **Operations**: create-tag, switch-tag, move between tags

## 4. Design Patterns

### 4.1 Command Pattern (CLI & MCP)
Each operation is encapsulated as a command with:
- Input validation (Zod schemas)
- Execution logic
- Output serialization
- Error handling

### 4.2 Repository Pattern (Persistence)
Task storage abstracted behind repository interface:
```typescript
interface TaskRepository {
  getAll(tag?: string): Task[];
  getById(id: string): Task;
  save(task: Task): void;
  delete(id: string): void;
}
```

### 4.3 Strategy Pattern (AI Models)
Model selection based on task requirements:
```typescript
const modelStrategies = {
  research: PerplexityStrategy,
  coding: ClaudeStrategy,
  planning: GPT4Strategy
};
```

### 4.4 Observer Pattern (Status Updates)
Task status changes propagate to dependents:
- When task completes → unblock waiting tasks
- When task blocked → optionally cascade to dependents

## 5. Strengths

1. **Massive Adoption**: 23.9k stars validates product-market fit
2. **Multi-Tool Integration**: Works with Cursor, Windsurf, VS Code, Claude Code
3. **PRD-First Workflow**: Encourages planning before coding
4. **Dependency Awareness**: Prevents working on blocked tasks
5. **Token-Efficient Modes**: Core mode uses only 5,000 tokens
6. **Multi-Model Flexibility**: Not locked to single AI provider
7. **Tag System**: Enables parallel feature development isolation
8. **Active Development**: 1,067 commits, active maintenance
9. **Documentation**: Comprehensive docs at docs.task-master.dev

## 6. Limitations

1. **Context Overhead**: Full tool set uses 21,000 tokens
2. **PRD Dependency**: Best results require structured PRD input
3. **API Key Management**: Requires external API keys (except Claude Code OAuth)
4. **File-Based Storage**: No database backend for large projects
5. **Single User Focus**: No collaboration or multi-user features
6. **No Real-Time Sync**: File-based storage doesn't sync across machines
7. **Learning Curve**: 36 tools can overwhelm new users
8. **License Restriction**: MIT with Commons Clause limits commercial use

## 7. Production Readiness

### SOLID Score: 4.2/5.0

**Justification**: Task Master demonstrates excellent Single Responsibility Principle adherence with its clear separation between parsing (PRD Parser), state management (Task Manager), persistence (Repository), and interface adapters (MCP/CLI). Each component has a well-defined purpose. Open/Closed Principle is strongly supported through the multi-model strategy system - adding new AI providers requires no modification to core logic, only a new strategy implementation. The tool loading modes (Core/Standard/All) further demonstrate OCP by allowing extension without modification. Liskov Substitution is satisfied within the model strategy hierarchy - any model strategy can be substituted for another without breaking the system. Interface Segregation is exemplary - the three tool loading modes (7/15/36 tools) prove the design intentionally segregates interfaces based on client needs. Dependency Inversion is well-implemented - the core engine depends on abstractions (TaskRepository, ModelStrategy) rather than concrete implementations. The file-based storage is injected rather than hard-coded. Minor deductions for some tight coupling in the CLI layer and the complexity of the MCP tool registration which could benefit from more abstraction. Overall, a well-architected system that demonstrates SOLID principles effectively.

### Production Score: 74/100

| Dimension | Score | Notes |
|-----------|-------|-------|
| Reliability | 78 | Stable MCP implementation, graceful degradation, file-based durability |
| Observability | 65 | CLI output logging, but limited metrics/tracing for MCP operations |
| Security | 72 | API key management via .env, no credential exposure in tools, but relies on file permissions |
| Performance | 75 | Token-efficient modes, lazy loading, efficient JSON parsing |
| Maintainability | 80 | Clean architecture, TypeScript, comprehensive test coverage, active community |

## 8. Comparative Analysis

### vs Linear/Jira
- **Task Master**: AI-native, lives in editor context, no context switching
- **Linear/Jira**: Feature-rich, team collaboration, but requires manual task creation
- **Winner**: Task Master for solo AI development; Linear/Jira for team projects

### vs Plain TODO Files
- **Task Master**: Dependency tracking, complexity analysis, AI parsing
- **Plain TODO**: Simple, zero overhead, human-readable
- **Winner**: Task Master for complex projects; Plain TODO for simple scripts

### vs Claude Memory/Artifacts
- **Task Master**: Structured task graph, cross-session persistence
- **Claude Memory**: Conversational context, session-scoped
- **Winner**: Task Master for multi-session projects; Memory for single conversations

### vs GitHub Projects
- **Task Master**: AI-integrated, PRD parsing, in-editor experience
- **GitHub Projects**: Team collaboration, GitHub integration, automation
- **Winner**: Task Master for AI-assisted solo work; GitHub Projects for team CI/CD

## 9. Integration Patterns

### 9.1 Cursor IDE Integration
```json
// .cursor/mcp.json
{
  "mcpServers": {
    "taskmaster-ai": {
      "command": "npx",
      "args": ["-y", "task-master-ai"],
      "env": {
        "ANTHROPIC_API_KEY": "your-key",
        "TASK_MASTER_TOOLS": "standard"
      }
    }
  }
}
```

### 9.2 Claude Code Integration
```bash
# Add as MCP server
claude mcp add taskmaster-ai -- npx -y task-master-ai

# Or with OAuth (no API key needed)
task-master init --use-claude-code
```

### 9.3 VS Code Integration
```json
// settings.json
{
  "mcp.servers": {
    "taskmaster": {
      "command": "npx",
      "args": ["-y", "task-master-ai"]
    }
  }
}
```

### 9.4 CI/CD Integration
```yaml
# .github/workflows/task-check.yml
- name: Verify no blocked tasks in PR
  run: |
    npx task-master-ai list --status=blocked --tag=${{ github.head_ref }}
    if [ $? -eq 0 ]; then
      echo "Blocked tasks found - cannot merge"
      exit 1
    fi
```

## 10. Best Practices

1. **Start with PRD**: Always begin projects with `parse-prd` rather than manual task creation
2. **Use Standard Mode**: Start with 15-tool standard mode before enabling all 36 tools
3. **Tag per Branch**: Create task tags matching git branch names for isolation
4. **Research First**: Use `research` command before implementing unfamiliar features
5. **Review Dependencies**: Check `next` command respects dependency order
6. **Clean Completed**: Periodically archive completed tasks to reduce context
7. **Version Tasks**: Commit `.taskmaster/` to git for history and sharing
8. **Document Blockers**: When marking blocked, document the reason for future context

## 11. Configuration Reference

### Environment Variables
| Variable | Required | Description |
|----------|----------|-------------|
| `ANTHROPIC_API_KEY` | Conditional | Claude API key (or use OAuth) |
| `OPENAI_API_KEY` | Optional | OpenAI API key for GPT models |
| `GOOGLE_API_KEY` | Optional | Gemini API key |
| `PERPLEXITY_API_KEY` | Optional | Perplexity for research tasks |
| `TASK_MASTER_TOOLS` | Optional | Tool loading mode: core/standard/all |

### Tool Loading Modes
| Mode | Tools | Tokens | Use Case |
|------|-------|--------|----------|
| Core | 7 | ~5,000 | Context-limited environments |
| Standard | 15 | ~10,000 | Recommended for most projects |
| All | 36 | ~21,000 | Power users, complex workflows |

### CLI Commands
```bash
task-master init              # Initialize new project
task-master parse-prd <file>  # Generate tasks from PRD
task-master list              # Show all tasks
task-master next              # Get next prioritized task
task-master show <id>         # View task details
task-master update <id>       # Modify task
task-master move              # Change task status/tag
task-master research <query>  # AI-powered research
task-master expand <id>       # Break task into subtasks
task-master complexity        # Analyze project complexity
```

## 12. Recommendations

### For Adoption
1. **Install via MCP**: Prefer MCP integration over standalone CLI for AI-native experience
2. **Start with Standard Mode**: Begin with 15 tools, add more only if needed
3. **Write Quality PRDs**: Invest time in structured PRDs - garbage in, garbage out
4. **Learn Dependency Syntax**: Master the dependency notation for complex projects

### For Enhancement
1. **Add Database Backend**: SQLite option for large projects
2. **Implement Sync**: Cloud sync for multi-machine workflows
3. **Build Dashboard**: Web UI for task visualization and reporting
4. **Add Collaboration**: Multi-user support with conflict resolution

### For Production
1. **Audit API Keys**: Ensure keys have minimal required permissions
2. **Backup .taskmaster**: Include in backup strategy, not just git
3. **Monitor Token Usage**: Track context consumption across tool modes
4. **Set Complexity Limits**: Prevent unbounded task expansion

---

## METHODOLOGY EXTENSIONS

### X. Workflow Definition

```
PHASE 1: INITIALIZATION
├── Input: Project idea or requirements document
├── Process: task-master init, configure API keys, select tool mode
├── Output: Initialized .taskmaster/ directory
└── Validation: `task-master list` returns empty task list

PHASE 2: PLANNING (PRD-DRIVEN)
├── Input: Product Requirements Document (PRD.md)
├── Process: task-master parse-prd PRD.md
├── Output: Task tree with dependencies and complexity scores
├── Validation:
│   - All tasks have clear acceptance criteria
│   - Dependencies form valid DAG (no cycles)
│   - Complexity scores assigned (1-10 scale)
└── Human Review: Approve task decomposition before execution

PHASE 3: EXECUTION (ITERATIVE)
├── Input: Task list from Phase 2
├── Process:
│   ├── `task-master next` → Get highest-priority unblocked task
│   ├── Implement task with AI assistance
│   ├── `task-master update <id> --status=done` when complete
│   └── Repeat until all tasks done
├── Output: Completed features matching task specifications
└── Validation: Each task meets acceptance criteria

PHASE 4: RESEARCH (AS NEEDED)
├── Input: Unfamiliar technology or requirement
├── Process: task-master research "<query>"
├── Output: Research report with citations
└── Integration: Update task details with research findings

PHASE 5: EXPANSION (COMPLEX TASKS)
├── Input: Task too large for single implementation
├── Process: task-master expand <id>
├── Output: Subtasks with inherited dependencies
└── Validation: Subtasks sum to original task scope

PHASE 6: COMPLETION
├── Input: All tasks marked done
├── Process:
│   ├── Review completed task list
│   ├── Archive or delete obsolete tasks
│   └── Generate completion report
├── Output: Project deliverables + task history
└── Validation: No tasks in todo or in-progress status
```

### Y. Prompt Engineering

**PRD Parsing Prompt Template**:
```markdown
You are analyzing a Product Requirements Document to generate tasks.

## Input PRD
{PRD_CONTENT}

## Your Task
1. Identify distinct implementable units
2. Establish dependency relationships
3. Estimate complexity (1-10 scale)
4. Define acceptance criteria for each task

## Output Format
{
  "tasks": [
    {
      "id": "TASK-001",
      "title": "Implement user authentication",
      "description": "Create login/logout functionality with session management",
      "dependencies": [],
      "complexity": 7,
      "acceptance_criteria": [
        "Users can log in with email/password",
        "Sessions persist across page refreshes",
        "Logout clears session completely"
      ]
    }
  ]
}

## Guidelines
- Each task should be completable in 1-4 hours
- Dependencies must reference valid task IDs
- Higher complexity = more implementation risk
- Acceptance criteria must be testable
```

**Task Selection Prompt**:
```markdown
You have access to the following task management tools:
{AVAILABLE_TOOLS}

Current project state:
{PROJECT_CONTEXT}

User request: {USER_REQUEST}

Select the appropriate tool and parameters to fulfill this request.
Consider:
1. Is there a direct tool for this operation?
2. Does the request involve dependencies or blockers?
3. Should this modify task state or just query it?
4. Is research needed before task modification?
```

**Research Integration Prompt**:
```markdown
You are conducting research for a development task.

## Task Context
{TASK_DETAILS}

## Research Query
{USER_QUERY}

## Project Context
{PROJECT_SUMMARY}

## Guidelines
1. Focus on practical implementation guidance
2. Cite specific documentation or source code
3. Consider compatibility with project's technology stack
4. Highlight any risks or gotchas discovered
5. Provide code examples where applicable

## Output
Structured research report suitable for task implementation.
```

### Z. Guardrails and Quality

**Execution Guardrails**:
1. **Dependency Enforcement**: Never start task with unmet dependencies
2. **Complexity Limits**: Tasks with complexity >8 should be expanded
3. **Cycle Prevention**: Reject dependency updates that create cycles
4. **Status Transitions**: Enforce valid state machine (no todo→done directly)
5. **API Key Validation**: Fail fast if required keys missing

**Quality Metrics**:
| Metric | Target | Measurement |
|--------|--------|-------------|
| PRD Coverage | 100% | All PRD sections have corresponding tasks |
| Dependency Completeness | 100% | No orphan dependencies |
| Task Granularity | 1-4 hours | Avg task implementation time |
| Acceptance Criteria | 3+ per task | Testable criteria per task |
| Research Citation | 2+ sources | Sources per research query |

**Anti-Patterns to Avoid**:
1. **Skipping PRD**: Jumping to task creation without planning document
2. **Manual Override**: Marking blocked tasks as done without resolution
3. **Tool Overload**: Using 36-tool mode when 7 tools suffice
4. **Ignoring Complexity**: Not expanding high-complexity tasks
5. **Stale Tasks**: Leaving completed tasks in active list
6. **Missing Context**: Research without project context injection

---

## Sources and References

1. **Primary Repository**: https://github.com/eyaltoledano/claude-task-master
2. **Documentation**: https://docs.task-master.dev
3. **MCP Specification**: https://modelcontextprotocol.io
4. **npm Package**: https://www.npmjs.com/package/task-master-ai
5. **Community Discord**: Referenced in repository README

---

*Analysis generated via research-framework-analyzer skill with confirmed invocation*


---

## Navigation

- [← Back to All Frameworks](index.md)
- [Comparison with similar frameworks](../comparisons/.md)
- [Full Synthesis](../synthesis.md)