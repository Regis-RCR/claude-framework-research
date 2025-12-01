---
title: Claude Squad
layout: default
parent: Frameworks
---

# Claude Squad

<div class="framework-meta">
<strong>Version:</strong> 1.0.13 |
<strong>Repository:</strong> <a href="https://github.com/smtg-ai/claude-squad">GitHub</a> |
<strong>License:</strong> AGPL-3.0
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: cli</span>
<span class="badge badge-exec">exec: multi-agent, parallel</span>
<span class="badge badge-function">function: orchestration</span>
<span class="badge badge-ecosystem">ecosystem: agnostic</span>
<span class="badge badge-scope">scope: session-level</span>
<span class="badge badge-integration">integration: full-setup</span>
<span class="badge badge-user">user: solo-dev</span>
<span class="badge badge-complexity">complexity: high</span>
<span class="badge badge-maturity">maturity: beta</span>
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
<td>4.0/5.0 ⭐⭐⭐⭐☆</td>
<td><strong>Overall</strong></td>
<td>68/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>0.0/5.0</td>
<td>Reliability</td>
<td>0</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>0.0/5.0</td>
<td>Observability</td>
<td>0</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>0.0/5.0</td>
<td>Security</td>
<td>0</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>0.0/5.0</td>
<td>Performance</td>
<td>0</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>0.0/5.0</td>
<td>Maintainability</td>
<td>0</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Git worktree-based parallel isolation</li>
<li>Terminal-native tmux orchestration</li>
<li>Agent-agnostic architecture</li>
<li>Zero-configuration multi-agent</li>
<li>4-12x productivity gains for parallelizable work</li>
</ul>

## Best For

<ul class="compact-list">
<li>Large-scale refactoring projects</li>
<li>Parallel feature development</li>
<li>Bug fixing sprints</li>
<li>Code modernization campaigns</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Windows requires WSL (tmux dependency)</li>
<li>GitHub dependency (gh CLI)</li>
<li>Not for simple sequential tasks</li>
</ul>

---

## Full Analysis

# Claude Squad - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-toolkit:research-framework-analyzer")
> - Template Version: 1.1
> - Category: orchestrator

## 1. Executive Summary

Claude Squad is a terminal-native multi-agent orchestrator that enables parallel execution of AI coding agents through git worktree isolation and tmux session management. With 5.2k GitHub stars and rapid adoption since April 2025, it has become the de facto standard for parallel Claude Code development workflows, supporting Claude Code, Aider, Codex, Gemini, OpenCode, and Amp agents.

**Key Value Proposition**: Solves the fundamental multi-agent conflict problem by leveraging git worktrees for filesystem isolation and tmux for session multiplexing, enabling developers to parallelize independent tasks and achieve 4-12x productivity gains.

**Primary Innovation**: Architectural isolation through git worktrees - each agent operates in a completely isolated working directory with its own branch, eliminating merge conflicts during parallel execution by preventing them entirely through resource separation.

## 2. Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                       TUI LAYER (cs)                             │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              Terminal User Interface                      │   │
│  │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐        │   │
│  │  │ Session │ │  Task   │ │ Status  │ │ Output  │        │   │
│  │  │  List   │ │ Preview │ │  Panel  │ │  View   │        │   │
│  │  └─────────┘ └─────────┘ └─────────┘ └─────────┘        │   │
│  │                                                           │   │
│  │  Commands: n(new) D(delete) ↵(attach) s(push) r(resume)  │   │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    ORCHESTRATION LAYER                           │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │              Session Manager (Go)                         │   │
│  │  - Session lifecycle management                           │   │
│  │  - Agent spawning and monitoring                          │   │
│  │  - Worktree/branch coordination                           │   │
│  │  - Auto-accept mode handling                              │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                    ISOLATION LAYER                               │
│  ┌───────────────────────┐ ┌───────────────────────────────┐   │
│  │     TMUX Sessions     │ │      Git Worktrees            │   │
│  │                       │ │                               │   │
│  │  ┌─────┐ ┌─────┐     │ │  ~/.claude-squad/worktrees/   │   │
│  │  │ S1  │ │ S2  │ ... │ │  ├── session-1/ (branch-1)    │   │
│  │  └─────┘ └─────┘     │ │  ├── session-2/ (branch-2)    │   │
│  │                       │ │  └── session-N/ (branch-N)    │   │
│  │  Terminal isolation   │ │  Filesystem isolation         │   │
│  └───────────────────────┘ └───────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────┐
│                      AGENT LAYER                                 │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐   │
│  │ Claude  │ │  Aider  │ │  Codex  │ │ Gemini  │ │   Amp   │   │
│  │  Code   │ │         │ │         │ │         │ │         │   │
│  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘   │
│                                                                  │
│       Each agent runs in isolated tmux session + worktree       │
└─────────────────────────────────────────────────────────────────┘
```

**Architecture Pattern**: Terminal multiplexing with worktree isolation

The architecture elegantly combines two Unix primitives (tmux for process isolation, git worktrees for filesystem isolation) to create a robust multi-agent execution environment without complex distributed systems overhead.

## 3. Core Components

### 3.1 TUI Interface (`cs` binary)
- **Purpose**: Centralized control panel for all agent sessions
- **Technology**: Go-based terminal UI
- **Features**: Session list, task preview, status panel, output view
- **Keyboard-driven**: No mouse required, efficient navigation

### 3.2 Session Manager
- **Purpose**: Orchestrate agent lifecycle and coordination
- **Functions**: Spawn, monitor, attach, detach, terminate sessions
- **Auto-Accept**: Background task completion without user interaction
- **Health Monitoring**: Detect hung or failed agents

### 3.3 Tmux Integration
- **Purpose**: Terminal process isolation
- **Implementation**: Each agent runs in dedicated tmux session
- **Benefits**: Independent scrollback, detach/reattach, process isolation
- **Session Naming**: Predictable naming for scripting access

### 3.4 Git Worktree Manager
- **Purpose**: Filesystem isolation for conflict-free parallel work
- **Location**: `~/.claude-squad/worktrees/`
- **Branch Strategy**: One branch per session
- **Merge Workflow**: Push from worktree, merge in main repo

## 4. Design Patterns

### 4.1 Worktree Isolation Pattern
Each agent gets complete filesystem isolation:
```
Original Repo → Worktree 1 (branch: feature-A)
             → Worktree 2 (branch: feature-B)
             → Worktree 3 (branch: bugfix-C)
```

### 4.2 Session Multiplexing Pattern
Tmux provides terminal isolation:
```
cs start "Add login" → creates tmux session claude-squad-1
cs start "Fix API"   → creates tmux session claude-squad-2
cs attach 1          → attaches to claude-squad-1
```

### 4.3 Auto-Accept Pattern
Background execution without human intervention:
```
cs start --auto-accept "Refactor auth"
→ Agent runs autonomously
→ Changes applied automatically
→ User reviews after completion
```

### 4.4 Unix Composition Pattern
Leverages existing tools rather than reimplementing:
- tmux: Battle-tested terminal multiplexer
- git worktrees: Native git functionality
- gh: GitHub CLI for push/PR operations

## 5. Strengths

1. **True Parallelism**: Multiple agents work simultaneously without conflicts
2. **Zero Configuration**: Works out of the box with existing git repos
3. **Multi-Agent Support**: Claude Code, Aider, Codex, Gemini, OpenCode, Amp
4. **Unix Philosophy**: Composable, scriptable, minimal dependencies
5. **TUI Excellence**: Efficient keyboard-driven interface
6. **Background Mode**: Auto-accept enables unattended execution
7. **Session Persistence**: Work survives terminal close (tmux)
8. **Low Overhead**: Go binary, no runtime dependencies
9. **Active Development**: Regular releases, responsive maintainers

## 6. Limitations

1. **Tmux Dependency**: Requires tmux knowledge for advanced use
2. **Git Worktree Learning**: Unfamiliar concept for some developers
3. **Session Startup Issues**: Timeout problems with slow agent initialization
4. **AGPL License**: Restrictive for commercial closed-source use
5. **Single Machine**: No distributed multi-machine support
6. **Manual Merging**: User must merge branches after parallel work
7. **No Task Dependencies**: Can't express "run B after A completes"
8. **Limited Observability**: Basic status, no detailed metrics

## 7. Production Readiness

### SOLID Score: 4.0/5.0

**Justification**: Claude Squad demonstrates strong Single Responsibility Principle through clear component separation - the TUI handles display, Session Manager handles orchestration, tmux handles process isolation, and git worktrees handle filesystem isolation. Each component has one clear job. Open/Closed Principle is moderately supported - new agents can be added through configuration, but the core orchestration logic would need modification for fundamentally different agent types. Liskov Substitution is well-implemented at the agent level - Claude Code, Aider, Codex can be substituted for each other as they all implement the same agent interface (terminal-based AI assistant). Interface Segregation is good - the TUI exposes only the commands needed for session management, not internal orchestration details. Users interact through a clean, focused interface. Dependency Inversion is partially achieved - the system depends on abstract concepts (terminal sessions, file isolation) but has hard dependencies on tmux and git which cannot be easily substituted. The Unix tool composition is elegant but creates concrete dependencies. Minor deductions for the tight coupling to specific Unix tools and limited extensibility for non-standard agent types.

### Production Score: 68/100

| Dimension | Score | Notes |
|-----------|-------|-------|
| Reliability | 72 | Stable tmux foundation, but timeout issues with slow agents |
| Observability | 55 | Basic TUI status, no metrics/tracing infrastructure |
| Security | 70 | Local-only, worktree isolation, but relies on git permissions |
| Performance | 78 | Lightweight Go binary, minimal overhead, parallel execution |
| Maintainability | 65 | Clean Go code, but worktree/tmux complexity for debugging |

## 8. Comparative Analysis

### vs Claude Code Native
- **Claude Squad**: True parallel execution, isolated workspaces
- **Claude Code**: Single agent, sequential execution
- **Winner**: Squad for parallel tasks; Native for simple sequential work

### vs Claude Flow
- **Claude Squad**: Terminal-native, tmux-based, worktree isolation
- **Claude Flow**: DAG orchestration, dependency management
- **Winner**: Squad for independent parallel tasks; Flow for dependent workflows

### vs Claude Code Heavy
- **Claude Squad**: Process-level isolation via tmux
- **Claude Code Heavy**: Git worktree isolation via shell scripts
- **Winner**: Squad for TUI experience; Heavy for research workflows

### vs Screen/Tmux Manual
- **Claude Squad**: Purpose-built TUI, automatic worktree management
- **Manual**: Full flexibility, no abstraction overhead
- **Winner**: Squad for productivity; Manual for customization

## 9. Integration Patterns

### 9.1 Basic Installation
```bash
# Homebrew (macOS/Linux)
brew install claude-squad

# Manual installation
curl -sSL https://raw.githubusercontent.com/smtg-ai/claude-squad/main/install.sh | bash
```

### 9.2 Session Management
```bash
# Start new session with prompt
cs start "Add user authentication feature"

# Start in auto-accept mode
cs start --auto-accept "Refactor database layer"

# List all sessions
cs list

# Attach to session
cs attach 1
```

### 9.3 CI/CD Integration
```bash
# Scripted parallel tasks
cs start --auto-accept "Update dependencies"
cs start --auto-accept "Run security audit"
cs start --auto-accept "Generate API docs"

# Wait for completion
cs wait-all

# Collect results
cs push-all
```

### 9.4 Team Workflow
```bash
# Developer A: Feature work
cs start "Implement OAuth login"

# Developer A: Bug fix (parallel)
cs start "Fix session timeout bug"

# Both complete independently
# Merge branches via normal git workflow
```

## 10. Best Practices

1. **Use Descriptive Prompts**: Clear task descriptions help track sessions
2. **Enable Auto-Accept Carefully**: Only for well-understood, low-risk tasks
3. **Regular Push/Merge**: Don't let worktree branches diverge too long
4. **Clean Old Sessions**: Delete completed sessions to free resources
5. **Monitor Background Tasks**: Check auto-accept sessions periodically
6. **Use for Independent Tasks**: Best for parallelizable, non-dependent work
7. **Tmux Familiarity**: Learn basic tmux commands for advanced debugging
8. **Git Worktree Understanding**: Know how worktrees relate to main repo

## 11. Configuration Reference

### TUI Commands
| Key | Action |
|-----|--------|
| `n` | New session |
| `N` | New session with prompt |
| `D` | Delete session |
| `↵/o` | Attach to session |
| `ctrl-q` | Detach from session |
| `s` | Push changes |
| `c` | Checkout main |
| `r` | Resume agent |
| `q` | Quit TUI |

### CLI Commands
| Command | Description |
|---------|-------------|
| `cs start <prompt>` | Create new session |
| `cs list` | List all sessions |
| `cs attach <id>` | Attach to session |
| `cs delete <id>` | Delete session |
| `cs push <id>` | Push session changes |

### Environment Variables
| Variable | Default | Description |
|----------|---------|-------------|
| `CLAUDE_SQUAD_HOME` | `~/.claude-squad` | Base directory |
| `CLAUDE_SQUAD_AGENT` | `claude` | Default agent |

## 12. Recommendations

### For Adoption
1. **Install Prerequisites**: Ensure tmux and gh are available
2. **Start Small**: Try with 2-3 parallel sessions initially
3. **Learn Tmux Basics**: Understand attach/detach/scrollback
4. **Practice Merge Flow**: Comfortable with worktree → main merging

### For Enhancement
1. **Add Task Dependencies**: Express "run B after A"
2. **Improve Observability**: Add metrics and logging
3. **Distributed Support**: Multi-machine coordination
4. **Auto-Merge Option**: Automated conflict-free merging

### For Production
1. **Monitor Session Health**: Watch for timeout/hung agents
2. **Regular Cleanup**: Prune old worktrees and sessions
3. **Backup Strategy**: Include worktrees in backup plan
4. **Team Guidelines**: Document branch naming conventions

---

## ORCHESTRATOR EXTENSIONS

### X. Execution Model

**Parallel Execution Architecture**:
```
User invokes: cs start "Task A"
             cs start "Task B"
             cs start "Task C"

Execution:
┌─────────────────────────────────────────────────────┐
│                    cs TUI                           │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐              │
│  │Session 1│ │Session 2│ │Session 3│              │
│  │ Task A  │ │ Task B  │ │ Task C  │              │
│  └────┬────┘ └────┬────┘ └────┬────┘              │
└───────┼───────────┼───────────┼────────────────────┘
        │           │           │
        ▼           ▼           ▼
   [tmux:1]    [tmux:2]    [tmux:3]
   [wt:A]      [wt:B]      [wt:C]
        │           │           │
        └─────────┬─┴───────────┘
                  │
            [git push all]
                  │
                  ▼
            [main branch]
```

**Execution Modes**:
- **Interactive**: User reviews each agent action
- **Auto-Accept**: Agent runs autonomously, user reviews results
- **Background**: Agent runs detached, user reconnects later

### Y. State Management

**Session State**:
```
Session {
  id: string
  name: string
  prompt: string
  status: pending | running | completed | failed
  agent: claude | aider | codex | gemini | opencode | amp
  worktree_path: string
  branch_name: string
  tmux_session: string
  created_at: timestamp
  auto_accept: boolean
}
```

**Worktree State**:
- Each session owns exactly one worktree
- Worktree lifecycle tied to session lifecycle
- Branch automatically created/deleted with session

**Persistence**:
- Session metadata stored in `~/.claude-squad/`
- Worktrees persist in filesystem
- Tmux sessions survive terminal close

### Z. Inter-Agent Communication

**Current Model**: No direct agent communication
- Agents work independently in isolated worktrees
- Communication happens through git (push/merge)
- Human mediates any coordination needs

**Coordination Patterns**:
```
Pattern 1: Sequential Merge
Agent A completes → push → merge to main
Agent B pulls main → continues work → push → merge

Pattern 2: Parallel Merge (conflict-free)
Agent A: src/auth/
Agent B: src/api/
Both complete → push → merge (no conflicts)

Pattern 3: Manual Conflict Resolution
Agent A & B modify same files
Push both → human resolves conflicts
```

### W. Scalability

**Scaling Characteristics**:
- **Horizontal**: Limited by machine resources (CPU, memory, disk)
- **Vertical**: Each session adds fixed overhead (~50MB tmux + agent)
- **Practical Limit**: 5-10 concurrent sessions on typical dev machine

**Resource Management**:
```
Session overhead:
- tmux session: ~5MB
- git worktree: Size of repo × 1 (shared objects)
- agent process: ~50-200MB (varies by agent)
- total per session: ~100-250MB

Recommended limits:
- Light machine (8GB): 3-4 sessions
- Medium machine (16GB): 6-8 sessions
- Heavy machine (32GB+): 10-15 sessions
```

**Bottlenecks**:
1. Disk I/O for large repos (worktree creation)
2. API rate limits (Claude/OpenAI)
3. Memory for multiple LLM-heavy agents
4. CPU for parallel compilation tasks

---

## Sources and References

1. **Primary Repository**: https://github.com/smtg-ai/claude-squad
2. **Official Website**: https://smtg-ai.github.io/claude-squad/
3. **Blog Post**: https://www.emsi.me/tech/ai-ml/tame-your-terminal-managing-ai-coding-agents-with-claude-squad/
4. **AIToolNet Review**: https://www.aitoolnet.com/claude-squad
5. **Git Worktrees Documentation**: https://git-scm.com/docs/git-worktree

---

*Analysis generated via research-framework-analyzer skill with confirmed invocation*


---

<footer class="generation-meta">
<small>
Generated: 2025-12-01 11:44 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/claude-squad">Source Data</a>
</small>
</footer>

<footer class="signature">∵ RCR Regis ∴</footer>