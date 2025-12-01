---
title: Claude Swarm / SwarmSDK
layout: default
parent: Frameworks
---

# Claude Swarm / SwarmSDK

<div class="framework-meta">
<strong>Version:</strong> 2.5.1 |
<strong>Repository:</strong> <a href="https://github.com/parruda/swarm">GitHub</a> |
<strong>License:</strong> MIT
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: sdk, cli</span>
<span class="badge badge-exec">exec: multi-agent, parallel</span>
<span class="badge badge-function">function: orchestration</span>
<span class="badge badge-ecosystem">ecosystem: python</span>
<span class="badge badge-scope">scope: session-level</span>
<span class="badge badge-integration">integration: full-setup</span>
<span class="badge badge-user">user: solo-dev, team</span>
<span class="badge badge-complexity">complexity: high</span>
<span class="badge badge-maturity">maturity: stable</span>
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
<td>4.1/5.0 ⭐⭐⭐⭐☆</td>
<td><strong>Overall</strong></td>
<td>80/100 🟢</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>4.5/5.0</td>
<td>Reliability</td>
<td>80</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>4.0/5.0</td>
<td>Observability</td>
<td>75</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>4.0/5.0</td>
<td>Security</td>
<td>82</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>4.0/5.0</td>
<td>Performance</td>
<td>85</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>4.0/5.0</td>
<td>Maintainability</td>
<td>80</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Single-process architecture (v2) eliminating MCP overhead</li>
<li>15x token efficiency via semantic memory search</li>
<li>SwarmMemory with FAISS indexing and local ONNX embeddings</li>
<li>Comprehensive hooks system (12 events, 6 action types)</li>
<li>Dual-version strategy (v1 multi-process, v2 single-process)</li>
<li>Node workflows for multi-stage pipelines</li>
</ul>

## Best For

<ul class="compact-list">
<li>Ruby/Rails development team automation</li>
<li>Multi-agent research workflows</li>
<li>Data processing pipelines</li>
<li>Development team simulation</li>
<li>Batch processing and automation</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Ruby ecosystem lock-in (Ruby >= 3.2.0)</li>
<li>Single-machine scaling only</li>
<li>Ruby GVL limits true parallelism</li>
<li>Learning curve for hook system complexity</li>
<li>Smaller community than JavaScript alternatives</li>
</ul>

---

## Full Analysis

# Claude Swarm / SwarmSDK Framework Analysis

**Analysis Version:** 1.0.0
**Framework Version:** 2.3.0
**Category:** orchestrator
**Analysis Date:** 2025-11-28
**Analyst:** Claude (via research-framework-analyzer skill)
**Skill Invocation:** Confirmed

---

## 1. Overview & Context

Claude Swarm (SwarmSDK) represents one of the earliest and most mature multi-agent orchestration frameworks for Claude, developed by Paulo Arruda. The project has undergone a significant architectural evolution from its initial multi-process approach to a sophisticated single-process Ruby architecture, representing a fundamental paradigm shift in multi-agent orchestration philosophy.

With nearly 1,500 GitHub stars and over 100 forks, SwarmSDK has established itself as the leading Ruby-based solution for AI agent orchestration. The project maintains two parallel implementations: Claude Swarm v1 (multi-process via MCP) and SwarmSDK v2 (single-process Ruby), allowing teams to choose the architecture that best fits their requirements.

SwarmSDK v2's primary innovation is decoupling from Claude Code entirely, eliminating Node.js dependencies and MCP inter-process communication overhead in favor of direct Ruby method invocations within a single process. This architectural decision yields a reported 15x token efficiency improvement through semantic memory search combined with significantly reduced communication latency.

The framework targets Ruby and Rails development teams seeking sophisticated multi-agent automation. Unlike JavaScript-centric solutions, SwarmSDK leverages Ruby's expressive DSL capabilities for elegant agent configuration while providing YAML alternatives for declarative definitions. The comprehensive hooks system (12 event types with 6 action categories) enables deep customization of agent behavior at every execution point.

Key differentiators include the SwarmMemory subsystem with FAISS-based semantic search and local ONNX embeddings, node workflows for multi-stage processing pipelines, and support for any LLM provider through RubyLLM abstraction. The project operates under MIT license and maintains an active release cadence with 44 releases demonstrating consistent evolution.

**Sources:**
- [GitHub Repository (v2)](https://github.com/parruda/swarm)
- [GitHub Repository (v1)](https://github.com/parruda/claude-swarm)
- [RubyGems - swarm_sdk](https://rubygems.org/gems/swarm_sdk)

---

## 2. Architecture & Design

### 2.1 Component Architecture

SwarmSDK v2 implements a layered single-process architecture:

```
┌─────────────────────────────────────────────────────────┐
│                    SwarmCLI (REPL/Batch)                │
├─────────────────────────────────────────────────────────┤
│                     SwarmSDK Core                       │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │    Agent    │  │   Workflow  │  │    Hooks    │     │
│  │  Executor   │  │   Engine    │  │   System    │     │
│  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘     │
│         │                │                │             │
│  ┌──────┴────────────────┴────────────────┴──────┐     │
│  │              Agent::Chat Layer                 │     │
│  └──────────────────────┬───────────────────────┘     │
├─────────────────────────┼───────────────────────────────┤
│  ┌──────────────────────┴───────────────────────┐     │
│  │               RubyLLM Interface               │     │
│  │    ┌───────┐  ┌───────┐  ┌───────┐          │     │
│  │    │Claude │  │OpenAI │  │Gemini │  ...     │     │
│  │    └───────┘  └───────┘  └───────┘          │     │
│  └──────────────────────────────────────────────┘     │
├─────────────────────────────────────────────────────────┤
│                     SwarmMemory                         │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐     │
│  │   FAISS     │  │    ONNX     │  │  Knowledge  │     │
│  │   Index     │  │  Embeddings │  │   Store     │     │
│  └─────────────┘  └─────────────┘  └─────────────┘     │
└─────────────────────────────────────────────────────────┘
```

The **SwarmSDK Core** manages agent lifecycle, delegation, and tool execution. The Agent::Chat layer (introduced in v2.3.0) provides composition over inheritance for conversation management. Workflow Engine handles node-based pipelines with dependency resolution.

The **RubyLLM Interface** abstracts LLM providers, enabling support for Claude, OpenAI, Gemini, and any other provider with a RubyLLM adapter. This decoupling from Claude-specific APIs is a key differentiator from v1.

**SwarmMemory** provides persistent semantic search capabilities using FAISS vector indexing and local ONNX embeddings. This enables agents to store and retrieve knowledge without external dependencies.

### 2.2 Data Flow

Agent execution follows a well-defined flow with hook integration:

```
User Prompt
     │
     ▼
┌────────────────────┐
│ on_user_message    │ ← Context injection hooks
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│  Context Builder   │ ← Memory retrieval
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│   RubyLLM Call     │ ← LLM completion
└─────────┬──────────┘
          │
     ┌────┴────┐
     │Tool Use?│
     └────┬────┘
          │ Yes
          ▼
┌────────────────────┐
│  on_pre_tool       │ ← Validation hooks
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│  Tool Execution    │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│  on_post_tool      │ ← Result processing
└─────────┬──────────┘
          │
          ▼
     (Loop to LLM)
          │
          ▼
┌────────────────────┐
│  on_pre_response   │ ← Quality gates
└─────────┬──────────┘
          │
          ▼
      Response
```

### 2.3 Integration Points

1. **LLM Provider Interface**: RubyLLM abstraction for multi-provider support
2. **Hook System**: 12 event types for execution interception
3. **Tool Registry**: 11 built-in tools with custom extension support
4. **Memory Interface**: SwarmMemory tools for persistent storage
5. **Configuration**: Dual YAML/Ruby DSL configuration
6. **Rails Integration**: ActiveJob and Rails application embedding

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

SwarmSDK supports planning through agent team composition:

**Team Definition:** Agents are defined with specialized roles and delegation hierarchies:
```yaml
agents:
  lead:
    role: "Lead developer coordinating the team"
    delegates_to: [frontend, backend, tester]
  frontend:
    role: "Frontend specialist for UI components"
  backend:
    role: "Backend developer for API and database"
```

**Context Injection:** Hooks inject project state at interaction start:
```yaml
hooks:
  on_user_message:
    - run: "git diff --stat"
      append_output_to_context: true
```

**Workflow Planning:** Node workflows define multi-stage pipelines with dependencies, enabling planned execution sequences.

### 3.2 Execution Phase

Execution support centers on delegation and tool orchestration:

**Delegation:** Lead agents distribute tasks to specialists:
```ruby
swarm.execute(
  agent: :lead,
  prompt: "Build user authentication feature"
)
# Lead delegates to backend for API, frontend for UI
```

**Non-Blocking Execution:** v2.3.0 introduced async execution:
```ruby
result = swarm.execute(agent: :lead, prompt: "Build TODO app", wait: false)
result.cancel if some_condition
result.wait  # Block when needed
```

**Tool Orchestration:** 11 built-in tools (Read, Write, Edit, Bash, Memory operations) execute within the single process with sub-millisecond overhead.

### 3.3 Review Phase

Review integration through hooks and quality gates:

**Quality Gates Pattern:**
```yaml
hooks:
  on_pre_response:
    - run: "npm run lint"
      stop_on_error: true
    - run: "npm test"
      stop_on_error: true
```

**Approval Workflows:** Interactive approval for sensitive operations:
```yaml
hooks:
  on_pre_tool:
    - run: |
        if [ "{{ tool_name }}" = "Bash" ]; then
          read -p "Approve? (y/n) " -n 1 -r
          [ "$REPLY" = "y" ] || exit 1
        fi
```

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle

The gem ecosystem demonstrates strong SRP: `swarm_sdk` for core orchestration, `swarm_cli` for command-line interface, `swarm_memory` for persistence. Each agent has a single role definition. Services (Agent, Workflow, Hooks) maintain focused responsibilities.

**Score: 4.5/5.0**

### 4.2 Open-Closed Principle

The plugin architecture enables extension without modification. New LLM providers integrate through RubyLLM adapters. Custom tools implement a standard interface. Hook actions extend behavior at defined points.

However, adding new event types requires framework modification.

**Score: 4.0/5.0**

### 4.3 Liskov Substitution Principle

LLM providers are substitutable through RubyLLM interface. Storage backends (SwarmMemory stores) implement consistent interfaces. Agent configurations in YAML or Ruby DSL produce equivalent runtime behavior.

**Score: 4.0/5.0**

### 4.4 Interface Segregation Principle

Tools expose focused interfaces (Read reads, Write writes). Memory operations separate into distinct tools (MemoryWrite, MemoryRead, MemorySearch). Configuration separates YAML (declarative) from Ruby DSL (programmatic) for different use cases.

**Score: 4.0/5.0**

### 4.5 Dependency Inversion Principle

High-level orchestration depends on abstractions (RubyLLM interface, not specific APIs). Storage depends on interface contracts. The Agent::Chat abstraction layer demonstrates composition over inheritance.

**Score: 4.0/5.0**

### 4.6 Practical Examples

**SRP Example - Gem Separation:**
```ruby
# Separate gems with focused responsibilities
require 'swarm_sdk'    # Core orchestration
require 'swarm_cli'    # CLI interface
require 'swarm_memory' # Persistent storage
```

**OCP Example - Custom Tool:**
```ruby
class MyTool < SwarmSDK::Tool
  def execute(params)
    # Custom logic
  end
end
# Register without modifying framework
swarm.register_tool(MyTool)
```

**Overall SOLID Score:** 4.1/5.0

**Justification:** SwarmSDK demonstrates thoughtful SOLID application throughout its architecture. The gem separation naturally enforces Single Responsibility at package level. Open-Closed adherence is strong through plugin and provider extensibility, though hook event types remain fixed. Interface Segregation appears in the tool system and configuration options. The v2.3.0 Agent::Chat abstraction exemplifies Dependency Inversion through composition. The Ruby ecosystem's conventions reinforce these patterns. Minor deductions reflect areas where framework internals require modification for certain extension types. Overall, the architecture represents mature Ruby engineering with principled design decisions.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**Test Coverage:** Custom RuboCop security cops provide static analysis. The project maintains active issue tracking with 89% closure rate.

**Error Handling:** Hook system includes `stop_on_error` controls. Error events (`on_error`) enable recovery logic. Non-zero exit codes halt execution when configured.

**Stability:** 44 releases demonstrate iterative stabilization. v2.3.0 represents major refactoring with maintained backward compatibility.

**Score: 80/100**

### 5.2 Observability

**Logging:** Built-in structured logging captures execution flow. Agent steps, tool executions, and delegation events are logged.

**Progress Tracking:** `on_agent_step` hooks enable custom progress reporting. REPL mode provides interactive visibility.

**Execution Tracing:** Snapshots capture state at execution points for debugging.

**Score: 75/100**

### 5.3 Security

**Permission System:** Fine-grained path and command restrictions:
```yaml
permissions:
  read_paths: [./src]
  bash_commands:
    allow: [npm, yarn]
    deny: [rm, sudo]
```

**Custom Security Linters:** RuboCop cops in `rubocop/cop/security/` enforce security patterns.

**Local Embeddings:** ONNX embeddings run locally, avoiding external API exposure.

**Score: 82/100**

### 5.4 Performance

**Token Efficiency:** 15x reduction via semantic memory search. Direct method calls eliminate IPC overhead.

**Memory:** Single-process architecture shares Ruby heap, reducing duplication. FAISS provides efficient vector search.

**Concurrency:** Non-blocking execution (v2.3.0) enables background processing. Ruby GVL limits true parallelism but async I/O mitigates for LLM calls.

**Score: 85/100**

### 5.5 Maintainability

**Documentation:** Comprehensive v2 documentation with 8-part tutorial series, reference guides, and integration examples.

**Code Quality:** Active maintenance with 15-20 commits/month. RuboCop integration enforces style consistency.

**Versioning:** Semantic versioning with detailed changelogs. Dual-version strategy (v1/v2) maintained simultaneously.

**Score: 80/100**

**Overall Production Score:** 80/100

---

## 6. Best Practices & Patterns

SwarmSDK codifies several patterns for multi-agent orchestration:

**Single-Process Efficiency Pattern:** Eliminating IPC overhead through direct method calls:
```ruby
# v1: Multi-process with MCP overhead
# v2: Direct Ruby invocation
agent.execute(prompt)  # Microseconds vs milliseconds
```

**Semantic Memory Pattern:** Knowledge retrieval through vector similarity:
```yaml
plugins:
  - swarm_memory
tools: [MemorySearch, MemoryWrite]
# Agent queries semantic index instead of full context replay
```

**Hook-Based Quality Gates:** Enforcing standards at execution boundaries:
```yaml
hooks:
  on_pre_response:
    - run: "bundle exec rspec"
      stop_on_error: true
    - run: "rubocop"
      stop_on_error: true
```

**Context Injection Pattern:** Automatic project state awareness:
```yaml
hooks:
  on_user_message:
    - run: "git status --short"
      append_output_to_context: true
```

**Dual Configuration Pattern:** YAML for declarative clarity, Ruby DSL for programmatic control:
```ruby
# Ruby DSL when logic needed
SwarmSDK.build do
  agent :dev do
    on_pre_tool { |ctx| validate(ctx) }
  end
end
```

---

## 7. Limitations & Trade-offs

**Ruby Ecosystem Lock-in:** The framework requires Ruby >= 3.2.0. Teams using Python or JavaScript face significant adoption friction. Rails integration is excellent, but non-Rails Ruby projects may find the dependencies heavy.

**Single-Machine Scaling:** The single-process architecture precludes horizontal scaling. Practical limits emerge around 15+ concurrent agents due to token management complexity. Distributed orchestration requires external solutions.

**Ruby GVL Constraints:** True parallelism is limited by Ruby's Global VM Lock. Async I/O mitigates for network-bound LLM calls, but CPU-intensive processing remains sequential.

**Learning Curve:** The comprehensive hook system (12 event types) and dual configuration options introduce complexity. Teams must understand both YAML and Ruby DSL patterns for full utilization.

**Community Size:** While strong within Ruby community, the user base is smaller than JavaScript alternatives. Ecosystem tooling (IDE support, debugging) may lag.

**v1/v2 Parallel Maintenance:** The dual-version strategy provides choice but fragments documentation and community attention.

---

## 8. Community & Ecosystem

SwarmSDK has cultivated a focused community within the Ruby ecosystem:

**Adoption Metrics:** 1,492 stars and 111 forks demonstrate solid Ruby community interest. The claude_swarm v1 gem has 98,124 downloads, indicating production usage.

**Maintenance Quality:** 89% issue closure rate and 88% PR acceptance demonstrate responsive maintenance. Only 7 open issues indicate manageable backlog.

**Release Cadence:** 44 releases with consistent monthly updates (15-20 commits) show active development. The maintainer (Paulo Arruda) remains engaged.

**Documentation:** Comprehensive v2 documentation includes getting started guides, 8-part tutorial series, CLI/DSL/YAML references, and Rails integration guides.

**Gem Ecosystem:** Four coordinated gems (swarm_sdk, swarm_cli, swarm_memory, claude_swarm) provide modular adoption paths.

---

## 9. Innovation & Differentiation

SwarmSDK introduces several innovations distinguishing it from alternatives:

**Single-Process Architecture:** The v1→v2 evolution eliminates MCP inter-process communication entirely. Direct Ruby method invocations achieve microsecond latency compared to millisecond MCP overhead, a fundamental performance improvement for agent coordination.

**15x Token Efficiency:** SwarmMemory's semantic search enables retrieval of only relevant knowledge rather than full context replay. FAISS indexing with local ONNX embeddings provides efficient similarity search without external API dependencies.

**Comprehensive Hook System:** 12 event types with 6 action categories provide unmatched execution interception. Hooks support context injection, quality gates, approval workflows, and custom automation at every execution point.

**Dual-Version Strategy:** Maintaining both v1 (multi-process MCP) and v2 (single-process) allows teams to choose architecture based on requirements. Process isolation vs. efficiency trade-offs are explicit choices rather than forced constraints.

**Ruby-Native Design:** Unlike ports or wrappers, SwarmSDK embraces Ruby idioms. The DSL configuration feels natural to Ruby developers. Rails integration is first-class rather than afterthought.

**Node Workflows:** Multi-stage pipelines with dependency management enable complex processing flows beyond simple agent delegation.

---

## 10. References & Sources

1. **GitHub Repository (v2):** https://github.com/parruda/swarm - SwarmSDK source
2. **GitHub Repository (v1):** https://github.com/parruda/claude-swarm - Claude Swarm source
3. **RubyGems - swarm_sdk:** https://rubygems.org/gems/swarm_sdk
4. **RubyGems - claude_swarm:** https://rubygems.org/gems/claude_swarm
5. **Documentation:** Repository /docs/v2 directory
6. **RubyLLM:** https://github.com/crmne/ruby_llm - LLM abstraction layer
7. **FAISS:** https://github.com/facebookresearch/faiss - Vector similarity search

---

## 11. Error Handling Patterns

### 11.1 Error Detection

Multi-layer error detection throughout the system:

**Hook Validation:** Shell commands return exit codes indicating success/failure.

**Tool Execution:** Tool implementations validate inputs and report errors through structured responses.

**LLM Errors:** RubyLLM captures API errors, rate limits, and malformed responses.

### 11.2 Error Recovery

**Error Event Hooks:**
```yaml
hooks:
  on_error:
    - run: "echo 'Error: {{ error_message }}' >> errors.log"
    - run: "./scripts/notify-team.sh"
```

**Stop on Error:** Configurable halting prevents cascade failures:
```yaml
hooks:
  on_pre_response:
    - run: "npm test"
      stop_on_error: true  # Halts if tests fail
```

**Retry Logic:** Agent execution can be retried based on error type. Non-blocking execution supports cancellation for graceful recovery.

### 11.3 Error Reporting

**Structured Logging:** Errors capture context including agent, tool, and execution state.

**Execution Logs:** Complete execution traces available for post-hoc analysis.

**Snapshot Debugging:** State snapshots at error points enable reproduction and investigation.

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

SwarmSDK implements aggressive token optimization:

**Semantic Memory Search:** Instead of full context replay, retrieve relevant knowledge:
```ruby
# Traditional: Pass entire conversation history
# SwarmSDK: Query semantic index
agent.tools[:MemorySearch].execute(query: "authentication patterns")
# Returns only relevant stored knowledge
```

**Reported Efficiency:** 15x token reduction compared to full context approaches.

**Context Compaction:** Delegation results are summarized before inclusion in parent context.

**Lazy Configuration:** Agent configurations load on-demand rather than eagerly.

### 12.2 Context Management

**Local Embeddings:** ONNX runtime generates embeddings locally, eliminating external API calls for vector operations.

**Result Truncation:** Tool outputs can be truncated to prevent context overflow.

**Memory Persistence:** Knowledge persists across sessions, avoiding repeated context building.

**Practical Scaling:**
- 2-8 agents: Excellent token efficiency
- 8-15 agents: Good with monitoring
- 15+ agents: Token management critical

---

## X. Multi-Agent Coordination Patterns

### X.1 Agent Communication

**Delegation Pattern:** Lead agents assign tasks to specialists:
```yaml
agents:
  lead:
    delegates_to: [frontend, backend, tester]
```

**Direct Method Calls:** Single-process architecture enables Ruby method invocations without serialization overhead.

### X.2 Task Distribution

**Role-Based Delegation:** Tasks route based on agent role specifications.

**Hierarchy Definition:** Delegation hierarchies defined declaratively in configuration.

**Dynamic Assignment:** Agents choose delegation targets based on task analysis.

### X.3 Result Aggregation

**Context Reconstruction:** v2.3.0 added delegation result event reconstruction for improved context management.

**Summary Injection:** Delegation results summarized before parent context inclusion.

**Workflow Aggregation:** Node workflows aggregate results at pipeline completion.

---

## Y. Context Management Strategy

### Y.1 Context Preservation

**SwarmMemory Persistence:** Knowledge persists beyond session boundaries through FAISS-indexed storage.

**Hook-Based Injection:** Context automatically populated via `on_user_message` hooks.

**Snapshot Capabilities:** State snapshots capture context at significant execution points.

### Y.2 Context Propagation

**Delegation Context:** Relevant context passes to delegated agents.

**Result Context:** Delegation results include sufficient context for parent understanding.

**Memory Tools:** Agents can query shared memory for cross-agent context.

### Y.3 Context Optimization

**Semantic Search:** Retrieve only relevant knowledge rather than full history.

**Summary Compaction:** Verbose results summarized before context inclusion.

**Session Scoping:** Scratchpad tool provides session-scoped temporary storage.

---

## Z. Tool Integration Architecture

The framework provides 11 built-in tools with extension capability:

**File Operations:**
- Read: File content retrieval
- Write: File creation/overwrite
- Edit: Section modification

**System Operations:**
- Bash: Shell command execution with permission controls

**Memory Operations:**
- MemoryWrite: Persistent knowledge storage
- MemoryRead: Knowledge retrieval
- MemoryEdit: Knowledge modification
- MemorySearch: Semantic similarity search
- LoadSkill: Dynamic capability loading
- Scratchpad: Session-scoped notes

**Agent Operations:**
- Delegate: Inter-agent task passing

**Permission System:**
```yaml
permissions:
  read_paths: [./src, ./tests]
  write_paths: [./src]
  bash_commands:
    allow: [npm, yarn, git]
    deny: [rm, sudo]
```

---

## W. Parallelization Approach

**Single-Process Concurrency:**
```ruby
# Non-blocking execution (v2.3.0)
result = swarm.execute(agent: :lead, prompt: "Task", wait: false)
```

**Ruby GVL Considerations:** Global VM Lock limits CPU parallelism. Async I/O mitigates for network-bound operations.

**Node Workflow Parallelization:** Pipeline stages can execute concurrently where dependencies allow.

**Practical Limits:**
- Ruby process memory bounds total agents
- GVL constrains CPU-intensive parallel work
- Async LLM calls provide effective concurrency for typical workloads


---

<footer class="generation-meta">
<small>
Generated: 2025-12-01 21:06 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/claude-swarm">Source Data</a>
</small>
</footer>