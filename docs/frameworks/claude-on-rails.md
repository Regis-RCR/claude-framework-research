---
title: Claude on Rails
layout: default
parent: Frameworks
---

# Claude on Rails

<div class="framework-meta">
<strong>Version:</strong> 0.2.0 |
<strong>Repository:</strong> <a href="https://github.com/obie/claude-on-rails">GitHub</a> |
<strong>License:</strong> MIT
</div>

## Classification

<div class="facets">
<span class="badge badge-tech">tech: sdk</span>
<span class="badge badge-exec">exec: single-agent</span>
<span class="badge badge-function">function: code-generation</span>
<span class="badge badge-ecosystem">ecosystem: ruby</span>
<span class="badge badge-scope">scope: project-level</span>
<span class="badge badge-integration">integration: code-integration</span>
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
<td>3.7/5.0 ⭐⭐⭐☆☆</td>
<td><strong>Overall</strong></td>
<td>68/100 🟡</td>
</tr>
<tr>
<td>S - Single Responsibility</td>
<td>3.8/5.0</td>
<td>Reliability</td>
<td>68</td>
</tr>
<tr>
<td>O - Open/Closed</td>
<td>3.5/5.0</td>
<td>Observability</td>
<td>52</td>
</tr>
<tr>
<td>L - Liskov Substitution</td>
<td>3.5/5.0</td>
<td>Security</td>
<td>72</td>
</tr>
<tr>
<td>I - Interface Segregation</td>
<td>4.0/5.0</td>
<td>Performance</td>
<td>60</td>
</tr>
<tr>
<td>D - Dependency Inversion</td>
<td>3.7/5.0</td>
<td>Maintainability</td>
<td>68</td>
</tr>
</tbody>
</table>
</div>

## Key Innovations

<ul class="compact-list">
<li>Multi-agent swarm for Rails (7 specialists)</li>
<li>Automatic agent orchestration from natural language</li>
<li>Rails-native understanding (conventions, patterns)</li>
<li>MCP integration (Rails, Turbo, Stimulus, Kamal docs)</li>
<li>Test-driven development as core feature</li>
</ul>

## Best For

<ul class="compact-list">
<li>Full-stack Rails feature implementation</li>
<li>Rapid API development with Rails conventions</li>
<li>Modern Rails stacks (Turbo, Stimulus, Rails 6+)</li>
</ul>

## Limitations

<ul class="compact-list">
<li>Rails 6+ only (no legacy support)</li>
<li>Token budget concerns for large projects</li>
<li>Non-Rails projects not supported</li>
<li>Early version (0.2.0)</li>
</ul>

---

## Full Analysis

# Claude on Rails - Framework Analysis

> **Analysis Metadata**
> - Date: 2025-11-28
> - Analyst: Claude (via research-framework-analyzer skill)
> - Skill Invocation: CONFIRMED via Skill("rcr-toolkit:research-framework-analyzer")
> - Template Version: 1.1
> - Category: domain-specific

**Framework:** Claude on Rails
**Version:** 0.2.0
**Category:** domain-specific
**Domain:** Ruby on Rails Development
**Repository:** https://github.com/obie/claude-on-rails
**License:** MIT
**Author:** Obie Fernandez
**GitHub Stars:** 646

---

## 1. Overview & Context

Claude on Rails is an innovative AI-powered development framework that transforms Claude Code into an intelligent team of specialized AI agents for Ruby on Rails development. Created by Obie Fernandez, author of "The Rails Way" and a prominent figure in the Rails community, the framework leverages the claude-swarm gem to orchestrate seven specialized agents that work collaboratively like a real development team.

### Core Value Proposition

The framework's fundamental innovation is **automatic agent orchestration** - developers describe features in natural language, and the system automatically delegates tasks to appropriate specialist agents without manual persona switching. This eliminates the cognitive overhead of context management while ensuring comprehensive coverage across all Rails layers.

### Key Differentiators

1. **Multi-Agent Swarm Architecture**: Seven specialized agents (Architect, Models, Controllers, Views, Services, Tests, DevOps) working in coordinated harmony
2. **Rails-Native Understanding**: Deep knowledge of Rails conventions, patterns, and best practices built into each agent
3. **MCP Server Integration**: Real-time access to Rails, Turbo, Stimulus, and Kamal documentation
4. **Zero Manual Persona Management**: Natural language task descriptions auto-route to appropriate specialists
5. **Test-Driven Development**: Comprehensive test generation as a core feature
6. **Domain Expertise**: Created by Rails authority Obie Fernandez

### Target Use Cases

**Optimal For:**
- Full-stack Rails feature implementation
- Rapid API development with Rails conventions
- Test-driven development workflows
- Modern Rails stacks (Turbo, Stimulus, Rails 6+)
- Medium-sized mature Rails applications

**Not Recommended For:**
- Legacy Rails applications (<6.0)
- Token budget-constrained environments
- Highly customized non-Rails architectures
- Very large codebases (>500K LOC)
- Non-Ruby/Rails projects

### Innovation

Claude on Rails is the first multi-agent swarm framework specifically designed for Rails development. By combining Obie Fernandez's deep Rails expertise with claude-swarm's orchestration capabilities, it delivers Rails-specific AI assistance that understands conventions, patterns, and best practices at a level generic AI tools cannot match.

**Source**: [GitHub Repository](https://github.com/obie/claude-on-rails), [RubyGems](https://rubygems.org/gems/claude-on-rails)

---

## 2. Architecture & Design

### 2.1 Component Architecture

Claude on Rails implements a **distributed multi-agent architecture** where specialized agents collaborate through a central orchestration layer:

```
                    ┌─────────────────┐
                    │    Developer    │
                    │  (Natural Lang) │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │    Architect    │
                    │  (Coordinator)  │
                    └────────┬────────┘
                             │
         ┌───────┬───────┬───┴───┬───────┬───────┐
         │       │       │       │       │       │
    ┌────▼──┐┌───▼───┐┌──▼──┐┌───▼───┐┌──▼──┐┌───▼───┐
    │Models ││Control││Views││Servic.││Tests││DevOps │
    └───────┘└───────┘└─────┘└───────┘└─────┘└───────┘
```

**Directory Structure:**

```
claude-on-rails/
├── .github/workflows/          # CI/CD automation
├── examples/
│   ├── e-commerce/             # E-commerce platform development
│   ├── api-only/               # API-only applications
│   ├── real-time/              # Real-time features with Turbo/Stimulus
│   └── performance/            # Performance optimization workflows
├── lib/claude_on_rails/        # Core framework code
│   ├── generators/             # Rails generators
│   └── templates/              # Agent prompt templates
├── spec/                       # Test suite
├── claude-on-rails.gemspec
└── README.md
```

**Technology Stack:**

| Component | Technology | Purpose |
|-----------|------------|---------|
| Language | Ruby (79%) | Rails ecosystem native |
| Orchestration | claude-swarm gem | Multi-agent coordination |
| Documentation | Rails MCP Server | Real-time Rails docs |
| Configuration | YAML | Swarm and agent setup |
| Testing | RSpec | Framework tests |

### 2.2 Data Flow

The orchestration follows a hub-and-spoke pattern with the Architect as coordinator:

```
Developer Input → Architect Analysis → Task Decomposition → Agent Delegation
                                                                    │
    ┌──────────────────────────────────────────────────────────────┤
    │                                                               │
    ▼                                                               ▼
Models Agent ──────┐                                    Controllers Agent
    │              │                                           │
    ▼              │                                           ▼
Views Agent ◄──────┴──────────────────────────────────► Services Agent
    │                                                           │
    └─────────────────────► Tests Agent ◄───────────────────────┘
                                │
                                ▼
                          DevOps Agent
```

**SwarmSDK v2 Foundation:**

```ruby
# claude-swarm.yml configuration
version: 1
swarm:
  name: "Rails Development Team"
  main: architect
  instances:
    architect:
      model: opus
      prompt: "@.claude-on-rails/prompts/architect.md"
      connections: [models, controllers, views, services, tests, devops]

    models:
      model: sonnet
      prompt: "@.claude-on-rails/prompts/models.md"
      directory: app/models
      connections: [architect, tests]
```

### 2.3 Integration Points

**Claude-Swarm Integration (Core):**
- Single-process orchestration in Ruby
- Direct method calls (no inter-process MCP communication)
- Persistent memory with semantic search
- Node workflows with dependencies
- Hooks system at 12 execution points

**Rails MCP Server Integration:**
- Real-time Rails Guides access
- Turbo documentation
- Stimulus reference
- Kamal deployment guides

**Post-Installation Structure:**

```
your-rails-app/
├── claude-swarm.yml              # Swarm configuration
├── CLAUDE.md                     # Project config (imports context.md)
└── .claude-on-rails/
    ├── context.md                # Rails project context
    └── prompts/                  # Agent-specific instructions
        ├── architect.md
        ├── models.md
        ├── controllers.md
        ├── views.md
        ├── services.md
        ├── tests.md
        └── devops.md
```

---

## 3. Development Cycle Integration

### 3.1 Planning Phase

**Support Level:** Full (Automatic orchestration)

The Architect agent handles task decomposition and planning:
- Analyzes natural language feature requests
- Identifies required Rails components
- Plans implementation sequence
- Assigns specialists automatically

**Example Workflow:**
```
"Add user authentication with email confirmation"
    ↓
Architect Analysis:
    - Models: User model with validations
    - Controllers: Auth logic, sessions
    - Views: Login forms, email templates
    - Services: Email service, tokens
    - Tests: Comprehensive RSpec coverage
    - DevOps: Email service configuration
```

### 3.2 Execution Phase

**Support Level:** Full (Highly automated)

Core development phase features:
- **Parallel Agent Execution**: Multiple agents work simultaneously on independent components
- **Automatic Delegation**: Hub-and-spoke coordination
- **Rails Convention Adherence**: All agents follow Rails patterns
- **Test Generation**: Tests agent produces comprehensive specs

**Coordination Patterns (12 supported):**
1. Hub & Spoke - Standard feature development
2. Pipeline Chain - Sequential handoffs
3. Parallel Swarm - Independent component work
4. Feedback Loop - Iterative improvement
5. Decision Tree - Smart task routing
6. Emergency Response - Crisis management
7. Circuit Breaker - Graceful failure handling
8. Actor Model - Async message passing
9. Load Balancer - Work distribution
10. Temporal Workflow - Time-based coordination
11. Saga Pattern - Distributed transactions
12. Observer Swarm - Event-driven reactions

### 3.3 Review Phase

**Support Level:** Full (Test-driven)

The Tests agent provides comprehensive review:
- Unit tests for models and services
- Request specs for controllers
- System tests for workflows
- Edge case coverage
- Self-correction via local spec execution

**Real-World Results:**
> "Complex ACL implementation took roughly two minutes of processing and cost only $4, with comprehensive RSpec tests." - Community Testimonial

---

## 4. SOLID Principles Adherence

### 4.1 Single Responsibility Principle

**Score: 4/5**

**Evidence:**
- Seven specialized agents, each with focused domain (Models for data, Controllers for routing, etc.)
- Framework enforces thin controllers pattern
- Service objects mandated for business logic
- Each agent has single prompt file

**Minor Violations:**
- Architect agent has dual responsibility (coordination + architectural decisions)
- Services agent handles both business logic and background jobs

### 4.2 Open-Closed Principle

**Score: 3.5/5**

**Evidence:**
- Agent system extensible via YAML configuration
- New agents added without modifying core code
- Prompt templates allow customization

**Violations:**
- Framework itself has limited extension points beyond agent configuration
- Generated code extensibility depends on prompt quality

### 4.3 Liskov Substitution Principle

**Score: 3/5**

**Evidence:**
- Agents follow common interface protocol (connections, directory scope, model assignment)
- SwarmSDK provides consistent delegation patterns

**Violations:**
- Not directly applicable to generated code
- Limited polymorphism recommendations in prompts

### 4.4 Interface Segregation Principle

**Score: 4.5/5**

**Evidence:**
- Excellent agent specialization - seven agents with focused interfaces
- Each agent exposes only domain-specific capabilities
- Controllers agent separated from API patterns
- Service objects enforce specific interfaces

**Minor Issue:**
- Architect agent interface slightly broad due to coordination role

### 4.5 Dependency Inversion Principle

**Score: 3.5/5**

**Evidence:**
- Agent delegation through SwarmSDK abstraction layer
- Service object pattern encourages dependency injection
- Result pattern decouples services from controllers

**Violations:**
- Generated Rails code often uses direct class dependencies
- Heavy coupling to Rails framework itself

### 4.6 Practical Examples

**Good Example - Service Object Pattern:**
```ruby
class UserRegistrationService
  def initialize(params)
    @params = params
  end

  def call
    ActiveRecord::Base.transaction do
      user = create_user
      send_confirmation(user)
      track_signup(user)
      Result.success(user)
    end
  rescue => e
    Result.failure(e.message)
  end
end
```

**Good Example - Thin Controller:**
```ruby
class UsersController < ApplicationController
  def create
    result = UserRegistrationService.new(user_params).call

    if result.success?
      render json: UserSerializer.new(result.user), status: :created
    else
      render json: { errors: result.errors }, status: :unprocessable_entity
    end
  end
end
```

**Overall SOLID Score:** 3.7/5.0

**Justification:** Claude on Rails demonstrates strong SOLID adherence through its multi-agent architecture (SRP, ISP) and Rails pattern enforcement. The primary weaknesses are in LSP (limited polymorphism) and DIP (Rails framework coupling). The 3.7 score reflects solid engineering principles applied to AI-assisted development with room for improvement in generated code flexibility.

---

## 5. Production Readiness Assessment

### 5.1 Reliability

**Score: 68/100**

- API stability: v0.2.0 marked as stable but framework experimental
- Breaking changes: v0.1.4 changed CLAUDE.md handling
- Session persistence: SwarmSDK memory system
- Issue closure rate: 25% (needs improvement)
- Upstream dependency: Sensitive to Claude Code CLI changes

### 5.2 Observability

**Score: 52/100**

- Logging: Standard Rails logging for generated code
- Metrics: No built-in token consumption monitoring
- Tracing: None for agent coordination
- Debugging: Limited subagent transparency
- Known gap: "Lack of transparency into what subagents are doing is a big problem" (Obie Fernandez)

### 5.3 Security

**Score: 72/100**

- Rails security patterns: Strong parameters, CSRF, XSS protection
- Authentication: Agent includes standard patterns
- Secrets: Delegates to Rails credentials
- Vulnerability: API keys in configuration require manual protection
- No CVEs reported

### 5.4 Performance

**Score: 60/100**

- Token consumption: Multi-agent architecture increases costs
- Startup time: Moderate (swarm initialization)
- Scaling: Performance degrades >100K LOC codebases
- Memory: SwarmSDK uses FAISS for semantic search
- Community report: Token consumption problematic for large monorepos

### 5.5 Maintainability

**Score: 68/100**

- Test coverage: RSpec suite for framework
- Code formatting: RuboCop enforced
- Documentation: README, examples, MCP server docs
- CI/CD: GitHub Actions workflows
- Dependency: Tightly coupled to claude-swarm gem

**Overall Production Score:** 68/100

**Assessment:** Claude on Rails is production-ready for development and staging environments. The framework demonstrates functional stability with strong Rails security patterns but lacks enterprise features. Experimental status, token consumption concerns, and limited observability warrant careful evaluation for production-critical systems.

---

## 6. Best Practices & Patterns

### Best Practices Applied

**1. Multi-Agent Swarm Pattern**

The core architectural pattern uses specialized agents coordinated by a central Architect:

```ruby
# Generated agent delegation in claude-swarm.yml
architect:
  model: opus
  role: "Lead developer coordinating Rails implementation"
  tools: [Read, Write, Edit, Bash]
  delegates_to: [models, controllers, views, services, tests, devops]
```

**Benefits:**
- Eliminates manual persona switching
- Ensures comprehensive coverage
- Deep domain expertise per agent

**2. Rails Convention Enforcement**

Agents enforce Rails conventions through prompt engineering:

```markdown
# Models Agent Instructions
## Conventions
- Use UUID primary keys
- Include timestamps on all models
- Soft delete pattern for critical data
- Database-level constraints mirror validations

## Anti-Patterns to Avoid
- Business logic in models (use services)
- Complex query chains (use query objects)
- Callbacks with side effects (use services)
```

**Benefits:**
- Consistent code generation
- Rails community alignment
- Reduced tech debt

**3. Service Object Pattern**

The framework mandates service objects for business logic:

```ruby
class UserRegistrationService
  include ActiveModel::Model

  def call
    ActiveRecord::Base.transaction do
      create_user
      create_profile
      send_confirmation
      track_signup
    end
    @result.success = true
    @result
  rescue ActiveRecord::RecordInvalid => e
    @result.errors = e.record.errors.full_messages
    @result
  end
end
```

**Benefits:**
- Thin controllers
- Testable business logic
- Transaction management

**4. Test-First Development Pattern**

The Tests agent generates comprehensive specs:

```ruby
RSpec.describe UserRegistrationService do
  describe '#call' do
    context 'with valid parameters' do
      it 'creates a user' do
        expect {
          described_class.new(valid_params).call
        }.to change(User, :count).by(1)
      end

      it 'sends a confirmation email' do
        expect {
          described_class.new(valid_params).call
        }.to have_enqueued_mail(UserMailer, :confirmation_email)
      end
    end
  end
end
```

**Benefits:**
- Comprehensive coverage
- Edge case handling
- Self-verification

---

## 7. Limitations & Trade-offs

### Architectural Trade-offs

**1. Multi-Agent Token Consumption**
- **Trade-off**: Seven agents consume more tokens than single-agent approaches
- **Benefit**: Deep specialization per domain
- **Impact**: Expensive for large codebases or long sessions
- **Mitigation**: Use model selection per agent (opus vs sonnet vs haiku)

**2. Rails Framework Lock-in**
- **Trade-off**: Only works with Rails applications
- **Benefit**: Deep Rails-specific expertise
- **Impact**: Non-Rails projects cannot use framework
- **Mitigation**: None (design decision)

**3. Ruby Version Requirement**
- **Trade-off**: Requires Ruby >= 3.3.0
- **Benefit**: Modern Ruby features, YJIT performance
- **Impact**: Legacy projects must upgrade Ruby
- **Mitigation**: Use rbenv/rvm for version management

### Known Limitations

**1. Subagent Transparency (Critical)**
- Cannot monitor individual agent execution
- Difficult to debug coordination issues
- No visibility into delegation decisions

**2. Token Consumption (High Impact)**
- Rapid token usage in multi-agent workflows
- Large codebases increase context requirements
- No built-in budget controls

**3. Context Decay**
- Agent performance degrades in extended sessions
- Need to restart for complex projects
- `/clear` required between major features

**4. Large Codebase Performance**
- Performance degrades >100K LOC
- Context window limitations
- Token costs scale with codebase size

**5. Issue Closure Rate**
- Only 25% issue closure rate
- Open bugs may affect stability
- Limited maintainer bandwidth

---

## 8. Community & Ecosystem

### Community Statistics

| Metric | Value |
|--------|-------|
| GitHub Stars | 637 |
| Forks | 34 |
| Contributors | 9 |
| Open Issues | 9 |
| Closed Issues | 3 |
| Total Downloads | 53,028 |
| RubyGems Version | 0.2.0 |

### Ecosystem Resources

**Author Authority:**
- Obie Fernandez: Author of "The Rails Way" (definitive Rails book)
- Recognized Rails community leader
- Active development and community engagement

**Dependency Ecosystem:**
- claude-swarm gem (parruda/claude-swarm)
- Rails MCP Server (maquina-app/rails-mcp-server)
- SwarmSDK v2 architecture

**Community Content:**
- Medium articles by Obie Fernandez
- Blog posts: enogrob, Hans Schnedlitz, Brandon Casci
- Use case testimonials: Rahoul Baruah

### Maintainer Responsiveness

- Average issue response: Variable
- Core maintainer: Obie Fernandez
- Community contributors: 9 active
- Release frequency: Rapid initial (6 in 7 days), then stable

---

## 9. Innovation & Differentiation

### Revolutionary Innovations

**1. First Multi-Agent Swarm for Rails**

Claude on Rails is the first framework to apply multi-agent swarm architecture specifically to Rails development:
- **Seven specialized agents** covering entire Rails stack
- **Automatic delegation** without manual persona switching
- **Rails convention enforcement** through agent prompts
- **Deep domain expertise** from Rails authority

**2. Natural Language Rails Development**

Unlike generic AI tools:
- Understands Rails conventions implicitly
- Generates convention-compliant code
- Produces comprehensive test suites
- Follows established Rails patterns

**3. MCP Documentation Integration**

Real-time access to canonical documentation:
- Rails Guides (version-specific)
- Turbo documentation
- Stimulus reference
- Kamal deployment guides
- Eliminates hallucination through canonical references

### Differentiation from Alternatives

| Feature | Claude on Rails | Generic AI | IDE Copilots |
|---------|----------------|------------|--------------|
| Rails specialization | ✅ Deep | ❌ Generic | ❌ Generic |
| Multi-agent | ✅ 7 agents | ❌ Single | ❌ Single |
| Auto-delegation | ✅ Yes | ❌ No | ❌ No |
| Rails MCP docs | ✅ Yes | ❌ No | ❌ No |
| Test generation | ✅ Comprehensive | ✅ Basic | ✅ Basic |
| Convention enforcement | ✅ Strong | ❌ Weak | ❌ Weak |

### Real-World Validation

**Case Studies:**
- ACL implementation: 2 minutes, $4 USD, comprehensive tests
- PDF comparison tool: Same-day deployment
- Race condition fix: Minutes vs hours traditional debugging

---

## 10. References & Sources

### Official Sources

1. **GitHub Repository**: https://github.com/obie/claude-on-rails
2. **RubyGems Package**: https://rubygems.org/gems/claude-on-rails
3. **Ruby Toolbox**: https://www.ruby-toolbox.com/projects/claude-on-rails

### Author Sources

4. Obie Fernandez - "Introducing ClaudeOnRails" (Medium)
   - https://obie.medium.com/introducing-claudeonrails-a25fb82ae37b

5. Obie Fernandez Twitter/X Announcement
   - https://x.com/obie/status/1938390578858807482

### Technical References

6. Claude-Swarm Repository
   - https://github.com/parruda/claude-swarm

7. Rails MCP Server
   - https://github.com/maquina-app/rails-mcp-server

8. SwarmSDK Documentation
   - https://github.com/parruda/swarm

### Community Sources

9. enogrob - Technical Deep Dive
   - https://enogrob.github.io/rails/ai/claude/development/swarm/2025/06/29/claudeonrails-ai-powered-rails-development-swarm.html

10. Hans Schnedlitz - Worktrees Workflow
    - https://www.hansschnedlitz.com/writing/2025/07/10/rails-claude-code-and-worktrees

11. Brandon Casci - CLAUDE.md Best Practices
    - https://www.brandoncasci.com/2025/07/30/from-chaos-to-control-teaching-claude-code-consistency.html

12. Rahoul Baruah - Use Case Testimonials
    - https://theartandscienceofruby.com/vibe-coding-with-claude-code/

---

## 11. Error Handling Patterns

### 11.1 Error Detection

**Service Result Pattern:**
```ruby
class Result
  attr_reader :value, :error

  def self.success(value)
    new(value: value)
  end

  def self.failure(error)
    new(error: error)
  end

  def success?
    error.nil?
  end

  def failure?
    !success?
  end
end
```

Services return Result objects enabling clean error handling.

**ActiveRecord Error Capture:**
```ruby
def call
  ActiveRecord::Base.transaction do
    # Operations
  end
  Result.success(user)
rescue ActiveRecord::RecordInvalid => e
  Result.failure(e.record.errors.full_messages)
rescue StandardError => e
  Result.failure(e.message)
end
```

### 11.2 Error Recovery

**Controller Error Handling:**
```ruby
class ApplicationController < ActionController::API
  rescue_from ActiveRecord::RecordNotFound, with: :not_found
  rescue_from ActiveRecord::RecordInvalid, with: :unprocessable_entity
  rescue_from ActionController::ParameterMissing, with: :bad_request

  private

  def not_found(exception)
    render json: { error: exception.message }, status: :not_found
  end

  def unprocessable_entity(exception)
    render json: { errors: exception.record.errors }, status: :unprocessable_entity
  end
end
```

**Graceful Degradation:**
- Agent coordination failures trigger fallback patterns
- Circuit breaker pattern for external integrations
- Transaction rollback on partial failures

### 11.3 Error Reporting

**Rails Standard Logging:**
```ruby
Rails.logger.error("Registration failed: #{e.message}")
```

**Structured Error Responses:**
```ruby
render json: {
  errors: result.errors,
  code: 'VALIDATION_FAILED',
  details: result.error_details
}, status: :unprocessable_entity
```

---

## 12. Token Efficiency Analysis

### 12.1 Token Optimization Strategies

**Model Selection Per Agent:**
```yaml
instances:
  architect:
    model: opus      # Best for coordination
  models:
    model: sonnet    # Good for implementation
  tests:
    model: haiku     # Cost-effective for test generation
```

**Context Conservation:**
- Clear context between features: `/clear`
- Break large features into smaller tasks
- Use specific agent prompts (reduce context)

**Session Management:**
- Limit sessions to 2-3 major features
- Start fresh for unrelated work
- Use git worktrees for isolation

### 12.2 Context Management

**CLAUDE.md Project Context:**
```markdown
# Project: MyApp

## Architecture
- Rails 7.1 full-stack application
- PostgreSQL database
- Sidekiq for background jobs

## Conventions
- Service objects for business logic
- Thin controllers, thin models
```

**Reference Pattern:**
```markdown
## Patterns
@.claude-on-rails/context.md
```

References files instead of inline content to reduce token usage.

### 12.3 Cost Estimates

| Codebase Size | Token Usage | Cost Impact |
|---------------|-------------|-------------|
| Small (<10K LOC) | Moderate | Acceptable |
| Medium (10K-50K) | High | Noticeable |
| Large (>50K LOC) | Very High | Significant |

**Mitigation Strategies:**
- Segment large tasks
- Use model tiering
- Implement token budgets externally

---

## X. Domain Expertise Depth

### X.1 Rails Convention Mastery

Claude on Rails demonstrates exceptional Rails convention knowledge through:

**Naming Conventions:**
- Snake_case for methods and variables (enforced)
- CamelCase for classes (enforced)
- Pluralized table names (enforced)
- RESTful route naming (enforced)

**Directory Structure Awareness:**
- Automatic detection of `app/models`, `app/controllers`, `app/views`
- Recognizes `app/services`, `app/jobs` for service objects
- Identifies test framework (RSpec vs Minitest)
- Detects API-only vs full-stack applications

**ActiveRecord Expertise:**

```ruby
class User < ApplicationRecord
  # Associations first
  has_many :posts, dependent: :destroy
  has_one :profile, dependent: :destroy

  # Validations second
  validates :email, presence: true, uniqueness: { case_sensitive: false }
  validates :name, presence: true, length: { minimum: 2 }

  # Scopes third
  scope :active, -> { where(active: true) }
  scope :confirmed, -> { where.not(confirmed_at: nil) }

  # Callbacks last
  before_save :normalize_email
end
```

### X.2 Rails Version Support

| Rails Version | Support Level | Notes |
|---------------|---------------|-------|
| 8.0+ | Full | Latest features |
| 7.0+ | Full | All features |
| 6.0+ | Full | Minimum required |
| < 6.0 | None | Not supported |

### X.3 Modern Rails Stack

**Hotwire Integration:**
- Turbo Frames for partial updates
- Turbo Streams for real-time updates
- Turbo Drive for SPA-like navigation
- Stimulus controllers generation

**Asset Pipeline:**
- Import maps support
- Propshaft compatibility
- esbuild/webpack integration
- CSS bundling

---

## Y. Specialized Tool Integration

### Y.1 Claude-Swarm Integration

**Core Dependency:**
```ruby
# Gemfile
gem 'claude_swarm', '~> 0.1'
```

**SwarmSDK v2 Features:**
- Single-process orchestration in Ruby
- Direct method calls (no inter-process MCP)
- Persistent memory with semantic search (FAISS)
- Node workflows with dependencies
- Hooks system at 12 execution points

### Y.2 Rails MCP Server

**Documentation Access:**
```bash
claude mcp add-json "railsMcpServer" '{"command":"ruby","args":["/path/to/rails-mcp-server/exe/rails-mcp-server"]}'
```

**Available Documentation:**
- Rails Guides (version-specific)
- Turbo documentation
- Stimulus reference
- Kamal deployment guides

**Setup Methods:**
1. During generation: `rails generate claude_on_rails:swarm` (press Y for MCP)
2. Manual: `bundle exec rake claude_on_rails:setup_mcp`
3. Status check: `bundle exec rake claude_on_rails:mcp_status`

### Y.3 Rails Generator Integration

**Installation:**
```bash
# Add to Gemfile
gem 'claude-on-rails', group: :development

# Install
bundle install

# Generate swarm configuration
rails generate claude_on_rails:swarm

# Launch swarm
claude-swarm
```

**Generated Artifacts:**
- `claude-swarm.yml` - Swarm configuration
- `CLAUDE.md` - Project context
- `.claude-on-rails/context.md` - Detailed context
- `.claude-on-rails/prompts/*.md` - Agent prompts

---

## Z. Use Case Coverage

### Z.1 Full-Stack Rails Development

**Primary Use Case:**
Natural language feature implementation across all Rails layers.

**Example Workflow:**
```
Input: "Add user authentication with email confirmation"

Output:
├── app/models/user.rb (User model with validations)
├── app/controllers/sessions_controller.rb (Auth logic)
├── app/controllers/confirmations_controller.rb (Email confirmation)
├── app/views/sessions/ (Login forms)
├── app/views/user_mailer/ (Email templates)
├── app/services/user_registration_service.rb (Business logic)
├── app/mailers/user_mailer.rb (Email delivery)
├── spec/models/user_spec.rb (Model tests)
├── spec/requests/sessions_spec.rb (Controller tests)
└── spec/services/user_registration_service_spec.rb (Service tests)
```

### Z.2 API-Only Applications

**Automatic Detection:**
- Views agent disabled for API-only projects
- API-specific patterns enabled
- JSON serialization patterns

**Generated Code:**
```ruby
class Api::V1::UsersController < ApplicationController
  before_action :authenticate_user!, except: [:create]

  def create
    @user = User.new(user_params)

    if @user.save
      render json: UserSerializer.new(@user), status: :created
    else
      render json: { errors: @user.errors }, status: :unprocessable_entity
    end
  end
end
```

### Z.3 Modern Rails Stacks

**Turbo/Stimulus Support:**
```erb
<%# app/views/users/new.html.erb %>
<%= turbo_frame_tag "user_form" do %>
  <div data-controller="form-validation">
    <%= form_with model: @user, data: { turbo_frame: "_top" } do |f| %>
      <div class="mb-4">
        <%= f.email_field :email,
            data: { action: "input->form-validation#validateEmail" } %>
      </div>
      <%= f.submit "Create Account" %>
    <% end %>
  </div>
<% end %>
```

### Z.4 Deployment Workflows

**Kamal Support:**
```yaml
# config/deploy.yml (generated by DevOps agent)
service: myapp
image: myapp

servers:
  web:
    hosts:
      - 192.168.0.1

env:
  clear:
    RAILS_ENV: production
  secret:
    - RAILS_MASTER_KEY
    - DATABASE_URL
```

### Z.5 Test-Driven Development

**Comprehensive Test Generation:**
```ruby
RSpec.describe UserRegistrationService do
  describe '#call' do
    context 'with valid parameters' do
      it 'creates a user'
      it 'creates a profile for the user'
      it 'sends a confirmation email'
      it 'tracks the signup event'
      it 'returns a successful result'
    end

    context 'with invalid email' do
      it 'does not create a user'
      it 'returns errors'
    end

    context 'with existing email' do
      it 'returns uniqueness error'
    end
  end
end
```

---

**Analysis Generated:** November 2025
**Template Version:** v1.1 (core + domain-specific extension)
**Sections:** 15 (12 core + 3 domain-specific X-Z)
**Word Count:** ~6,500 words


---

<footer class="generation-meta">
<small>
Generated: 2025-12-01 21:06 UTC |
Template: framework-page.md.j2 v2.0 |
<a href="https://github.com/Regis-RCR/Research-framework/tree/main/corpus/frameworks/claude-on-rails">Source Data</a>
</small>
</footer>