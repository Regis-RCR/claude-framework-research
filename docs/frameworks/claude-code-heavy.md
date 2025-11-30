---
title: claude-code-heavy
layout: default
parent: Frameworks
---

# claude-code-heavy

∵ RCR Regis ∴

**Category:** methodology
**Version:** 1.0.0
**Status:** Analyzed

## Scores

| Metric | Score | Rating |
|--------|-------|--------|
| SOLID Principles | 3.8/5.0 | ⭐⭐⭐☆☆ |
| Production Ready | 52/100 | 🟠 Alpha |

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

# Claude Code Heavy - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-toolkit:research-framework-analyzer")
> - Template Version: 1.1
> - Category: methodology

## 1. Executive Summary

Claude Code Heavy is a shell-based methodology for orchestrating parallel multi-agent research workflows using Git worktrees. The framework enables users to run 2-8 Claude Code CLI instances simultaneously, each in isolated worktrees with dedicated context, enabling comprehensive research tasks through intelligent planning and parallel execution. Originally developed to handle large-scale document analysis and codebase exploration, it provides a battle-tested approach to decomposing complex research questions into parallelizable subtasks.

**Key Value Proposition**: Transforms a single-threaded AI coding assistant into a parallel research team, with each agent maintaining full context isolation through Git's worktree mechanism, eliminating the cross-contamination of research threads common in sequential approaches.

## 2. Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    ORCHESTRATION LAYER                          │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              Planner Script (plan.sh)                    │   │
│  │  - Receives research question                            │   │
│  │  - Generates task decomposition                          │   │
│  │  - Creates worktree assignments                          │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                     EXECUTION LAYER                              │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐           │
│  │Worktree 1│ │Worktree 2│ │Worktree 3│ │Worktree N│           │
│  │ Agent A  │ │ Agent B  │ │ Agent C  │ │ Agent N  │           │
│  │(research)│ │(research)│ │(research)│ │(research)│           │
│  └────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘           │
│       │            │            │            │                   │
│       ▼            ▼            ▼            ▼                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │              Shared Results Directory                     │   │
│  │  - Markdown outputs per agent                             │   │
│  │  - Consolidated findings                                  │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                   SYNTHESIS LAYER                                │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              Synthesizer Script (synthesize.sh)          │   │
│  │  - Merges agent outputs                                  │   │
│  │  - Resolves conflicts                                    │   │
│  │  - Produces final report                                 │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

**Architecture Pattern**: Fan-out/Fan-in with worktree isolation

The architecture leverages Git worktrees as first-class isolation primitives. Each worktree provides a complete working directory pointing to the same repository but allowing independent file modifications. This means agents can write outputs, create temporary files, and explore code without interfering with each other.

## 3. Core Components

### 3.1 Planning Module (plan.sh)
- **Purpose**: Intelligent task decomposition for parallel execution
- **Input**: High-level research question or analysis request
- **Output**: N discrete task assignments with clear boundaries
- **Key Logic**: Uses Claude to analyze the question scope and determine optimal parallelization strategy

### 3.2 Execution Coordinator (run.sh)
- **Purpose**: Spawns and monitors parallel Claude Code instances
- **Functions**:
  - Creates worktrees dynamically (2-8 based on task complexity)
  - Launches Claude Code CLI in each worktree with task-specific prompts
  - Monitors progress and handles failures
  - Collects outputs to shared directory

### 3.3 Worktree Manager
- **Purpose**: Git worktree lifecycle management
- **Operations**: Create, list, prune, cleanup
- **Naming Convention**: `research-agent-{N}` where N is agent number

### 3.4 Synthesis Module (synthesize.sh)
- **Purpose**: Consolidates parallel research outputs
- **Functions**:
  - Reads all agent outputs from shared directory
  - Identifies overlaps and conflicts
  - Produces unified markdown report
  - Optionally triggers follow-up research rounds

## 4. Design Patterns

### 4.1 Fan-Out/Fan-In Pattern
The core workflow follows classic parallel processing:
1. **Fan-Out**: Single input decomposed into N parallel streams
2. **Independent Execution**: Each stream processes in isolation
3. **Fan-In**: Results merged into single consolidated output

### 4.2 Worktree Isolation Pattern
Git worktrees provide process-level isolation without container overhead:
- Same codebase, different working directories
- No file locking conflicts between agents
- Easy cleanup via `git worktree prune`

### 4.3 Prompt Template Pattern
Each agent receives standardized prompt structure:
```
TASK: {specific_research_question}
SCOPE: {files_or_directories_to_focus}
OUTPUT: Write findings to {output_path}
CONSTRAINTS: {time_limits, depth_limits}
```

## 5. Strengths

1. **Zero Infrastructure**: Pure shell + Git, no services to deploy
2. **True Isolation**: Worktrees eliminate cross-agent interference completely
3. **Linear Scaling**: Adding agents scales research throughput linearly (up to API limits)
4. **Familiar Tools**: Uses standard Git and Claude Code CLI - no new abstractions
5. **Debuggable**: Plain shell scripts, easy to trace and modify
6. **Cost-Effective**: Only pays for actual API calls, no orchestration overhead
7. **Reproducible**: Git-based state means full reproducibility of research sessions

## 6. Limitations

1. **Manual Coordination**: No automatic load balancing or dynamic task reallocation
2. **Limited Agent Communication**: Agents cannot share findings mid-execution
3. **Single-Machine Focus**: Not designed for distributed multi-machine scenarios
4. **No State Persistence**: Research sessions don't persist across runs
5. **Shell Complexity**: Complex logic in shell can become hard to maintain
6. **API Rate Limits**: Heavy parallel usage can hit Anthropic API limits
7. **No Progress Visibility**: Limited real-time visibility into agent progress

## 7. Production Readiness

### SOLID Score: 3.8/5.0

**Justification**: Claude Code Heavy demonstrates strong Single Responsibility Principle adherence with its distinct planning, execution, and synthesis modules. Each shell script has one clear purpose. Open/Closed Principle is moderately satisfied - adding new agent types is straightforward, but modifying core orchestration requires script changes. Liskov Substitution is N/A for this shell-based approach. Interface Segregation is well-handled with separate entry points for planning vs execution. Dependency Inversion is limited - scripts directly depend on Git and Claude Code CLI with no abstraction layer, which is acceptable for the simplicity goals but limits flexibility. The shell-based nature inherently limits some SOLID application, but within those constraints, the design is clean and focused.

### Production Score: 52/100

| Dimension | Score | Notes |
|-----------|-------|-------|
| Reliability | 55 | No retry logic, basic error handling, but Git isolation prevents data corruption |
| Observability | 35 | Minimal logging, no metrics, relies on file outputs for state |
| Security | 60 | No credential handling, relies on Claude Code CLI auth, worktrees are sandboxed |
| Performance | 65 | Excellent parallel throughput, limited only by API rate limits |
| Maintainability | 45 | Shell scripts can become complex, limited testing infrastructure |

## 8. Comparative Analysis

### vs Claude Squad
- **Claude Squad**: Process-level orchestration with terminal multiplexing
- **Claude Code Heavy**: Git worktree isolation with file-based coordination
- **Winner**: Claude Squad for real-time visibility; Heavy for research isolation

### vs Claude Flow
- **Claude Flow**: DAG-based task orchestration with dependencies
- **Claude Code Heavy**: Simple fan-out/fan-in without dependency graphs
- **Winner**: Flow for complex workflows; Heavy for parallel research

### vs Traditional Single-Agent
- **Single-Agent**: Sequential processing, context accumulation
- **Claude Code Heavy**: Parallel processing, isolated contexts
- **Winner**: Heavy for breadth; Single for depth with context

## 9. Integration Patterns

### 9.1 CI/CD Integration
```bash
# GitHub Actions example
- name: Run Heavy Research
  run: |
    ./plan.sh "Analyze security vulnerabilities in auth module"
    ./run.sh --agents 4
    ./synthesize.sh > security-report.md
```

### 9.2 Pre-Commit Hooks
```bash
# Run focused analysis before commits
./plan.sh "Review changes for bugs" --scope "$(git diff --name-only)"
./run.sh --agents 2
```

### 9.3 Scheduled Research
```bash
# Cron job for periodic codebase health checks
0 0 * * 1 cd /repo && ./plan.sh "Weekly code quality analysis" && ./run.sh
```

## 10. Best Practices

1. **Right-Size Agent Count**: Start with 2-4 agents; 8 only for truly parallelizable tasks
2. **Clear Task Boundaries**: Ensure task decomposition creates non-overlapping scopes
3. **Output Structure**: Standardize output format across agents for easier synthesis
4. **Cleanup Worktrees**: Run `git worktree prune` after sessions to avoid disk bloat
5. **Rate Limit Awareness**: Add delays between agent spawns if hitting API limits
6. **Monitor Outputs**: Check agent outputs mid-run for early failure detection
7. **Version Control Results**: Commit synthesized outputs for research reproducibility

## 11. Configuration Reference

### Environment Variables
| Variable | Default | Description |
|----------|---------|-------------|
| `HEAVY_AGENTS` | 4 | Number of parallel agents to spawn |
| `HEAVY_TIMEOUT` | 300 | Seconds before killing hung agents |
| `HEAVY_OUTPUT_DIR` | `./research-outputs` | Directory for agent outputs |
| `HEAVY_WORKTREE_PREFIX` | `research-agent` | Prefix for worktree names |

### Command Line Options
```bash
./run.sh [OPTIONS]
  --agents N       Number of agents (2-8)
  --timeout S      Timeout in seconds
  --output DIR     Output directory
  --dry-run        Plan only, don't execute
  --verbose        Enable debug logging
```

## 12. Recommendations

### For Adoption
1. **Start Small**: Begin with 2 agents on a well-defined research question
2. **Define Clear Outputs**: Specify exact output format expected from each agent
3. **Test Synthesis**: Ensure synthesis script handles edge cases (empty outputs, conflicts)

### For Enhancement
1. **Add Progress Tracking**: Implement simple progress file writing from agents
2. **Implement Retries**: Add retry logic for transient API failures
3. **Create Dashboard**: Simple web UI showing worktree status and outputs
4. **Add Metrics**: Log timing and token usage for cost tracking

### For Production
1. **Containerize**: Wrap in Docker for consistent environment
2. **Add Health Checks**: Monitor agent processes and restart if needed
3. **Implement Queuing**: Add task queue for managing API rate limits
4. **Persist Sessions**: Save research session state for resumability

---

## METHODOLOGY EXTENSIONS

### X. Workflow Definition

```
PHASE 1: PLANNING
├── Input: Research question + optional scope constraints
├── Process: Claude analyzes question, identifies parallelizable dimensions
├── Output: N task definitions with clear boundaries
└── Validation: Human review of task decomposition

PHASE 2: EXECUTION
├── Input: Task definitions from Phase 1
├── Process:
│   ├── Create N worktrees
│   ├── Launch Claude Code in each with task prompt
│   └── Monitor for completion/timeout
├── Output: N markdown files with research findings
└── Validation: Check all agents completed successfully

PHASE 3: SYNTHESIS
├── Input: N agent output files
├── Process: Claude merges outputs, resolves conflicts, identifies gaps
├── Output: Unified research report
└── Validation: Human review of final report

PHASE 4: ITERATION (Optional)
├── Input: Gaps identified in synthesis
├── Process: Generate follow-up tasks, repeat Phases 1-3
└── Output: Enhanced report with gap coverage
```

### Y. Prompt Engineering

**Planning Prompt Template**:
```
You are a research planning assistant. Given the following question:
{RESEARCH_QUESTION}

Decompose this into {N} independent research tasks that can be executed in parallel.
Each task should:
1. Have a clear, non-overlapping scope
2. Be completable in a single Claude Code session
3. Produce markdown output with specific sections

Output format:
TASK 1: [title]
SCOPE: [files/directories to focus on]
DELIVERABLE: [expected output sections]
...
```

**Agent Execution Prompt Template**:
```
You are Research Agent {N} of {TOTAL}.
Your specific task: {TASK_DESCRIPTION}
Your scope: {SCOPE_DEFINITION}

Write your findings to: {OUTPUT_PATH}

Structure your output as:
## Summary
## Key Findings
## Evidence
## Recommendations
## Open Questions

Stay within your assigned scope. Do not duplicate work from other agents.
```

**Synthesis Prompt Template**:
```
You are synthesizing research from {N} agents on: {RESEARCH_QUESTION}

Agent outputs:
{AGENT_1_OUTPUT}
---
{AGENT_2_OUTPUT}
---
...

Create a unified report that:
1. Consolidates overlapping findings
2. Resolves any conflicts (note the resolution)
3. Identifies gaps requiring follow-up
4. Provides executive summary and detailed sections
```

### Z. Guardrails and Quality

**Execution Guardrails**:
1. **Timeout Enforcement**: Kill agents exceeding timeout to prevent runaway costs
2. **Scope Containment**: Agents should only read files in their assigned scope
3. **Output Validation**: Check agent outputs exist and have minimum content
4. **Resource Limits**: Cap total agents to prevent API rate limit exhaustion

**Quality Metrics**:
| Metric | Target | Measurement |
|--------|--------|-------------|
| Task Overlap | <10% | Manual review of task definitions |
| Agent Success Rate | >90% | Completed agents / Total agents |
| Output Completeness | 100% | All expected sections present |
| Synthesis Coherence | Subjective | Human review of final report |
| Time Efficiency | <30min | Total wall-clock time for session |

**Anti-Patterns to Avoid**:
1. **Over-Parallelization**: Don't use 8 agents for a 2-agent task
2. **Vague Tasks**: "Research the codebase" is too broad
3. **Overlapping Scopes**: Agents stepping on each other's work
4. **Ignoring Synthesis**: Using raw agent outputs without consolidation
5. **No Iteration**: Stopping at first synthesis without gap analysis

---

## Sources and References

1. **Primary Repository**: https://github.com/gtrusler/claude-code-heavy
2. **Git Worktrees Documentation**: https://git-scm.com/docs/git-worktree
3. **Claude Code CLI Documentation**: https://docs.anthropic.com/claude-code
4. **Related Discussion**: Parallel AI coding assistants patterns

---

*Analysis generated via research-framework-analyzer skill with confirmed invocation*


---

## Navigation

- [← Back to All Frameworks](index.md)
- [Comparison with similar frameworks](../comparisons/methodology.md)
- [Full Synthesis](../synthesis.md)