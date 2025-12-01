---
title: Synthesis
layout: default
nav_order: 4
permalink: /synthesis/
---

# Framework Synthesis

Cross-framework analysis of 22 frameworks.

## Quick Stats

| Metric | Value | | Metric | Value |
|--------|-------|---|--------|-------|
| Total Frameworks | 22 | | Tech Approaches | 4 |
| Avg SOLID | 4.01/5.0 | | Avg Production | 72/100 |

## By Technical Foundation

<div class="facet-grid">
<div class="facet-card">
<h4>cli</h4>
<ul><li>Claude Flow</li><li>Claude Squad</li><li>Claude Swarm / SwarmSDK</li></ul>
</div>
<div class="facet-card">
<h4>mcp-native</h4>
<ul><li>Claude Task Master</li><li>NioPD (Nio Product Director)</li><li>Simone</li><li>taskmaster-mcp</li></ul>
</div>
<div class="facet-card">
<h4>prompt-based</h4>
<ul><li>Ab Method</li><li>BMAD Method (Build More, Architect Dreams)</li><li>CCPM (Claude Code PM)</li><li>claude-code-dev-kit</li><li>claude-code-heavy</li><li>ContextKit</li><li>Crystal</li><li>RIPER-5</li><li>Simone</li><li>SuperClaude</li><li>systemprompt-orchestrator</li></ul>
</div>
<div class="facet-card">
<h4>sdk</h4>
<ul><li>claude-code-by-agents</li><li>Claude on Rails</li><li>Claude Swarm / SwarmSDK</li><li>ClaudeKit</li><li>MoAI-ADK (Agentic Development Kit)</li><li>wshobson/agents</li></ul>
</div>
</div>

## By Execution Model

<div class="facet-grid">
<div class="facet-card">
<h4>multi-agent</h4>
<ul><li>claude-code-by-agents</li><li>Claude Flow</li><li>Claude Squad</li><li>Claude Swarm / SwarmSDK</li><li>MoAI-ADK (Agentic Development Kit)</li><li>systemprompt-orchestrator</li><li>wshobson/agents</li></ul>
</div>
<div class="facet-card">
<h4>parallel</h4>
<ul><li>Claude Flow</li><li>Claude Squad</li><li>Claude Swarm / SwarmSDK</li><li>wshobson/agents</li></ul>
</div>
<div class="facet-card">
<h4>sequential</h4>
<ul><li>Ab Method</li><li>BMAD Method (Build More, Architect Dreams)</li><li>claude-code-dev-kit</li><li>Crystal</li><li>RIPER-5</li></ul>
</div>
<div class="facet-card">
<h4>single-agent</h4>
<ul><li>BMAD Method (Build More, Architect Dreams)</li><li>CCPM (Claude Code PM)</li><li>claude-code-heavy</li><li>Claude on Rails</li><li>Claude Task Master</li><li>ClaudeKit</li><li>ContextKit</li><li>NioPD (Nio Product Director)</li><li>Simone</li><li>SuperClaude</li><li>taskmaster-mcp</li></ul>
</div>
</div>

## By Primary Function

<div class="facet-grid">
<div class="facet-card">
<h4>code-generation</h4>
<ul><li>Claude on Rails</li><li>ClaudeKit</li></ul>
</div>
<div class="facet-card">
<h4>context-management</h4>
<ul><li>CCPM (Claude Code PM)</li><li>ContextKit</li><li>Simone</li></ul>
</div>
<div class="facet-card">
<h4>dev-methodology</h4>
<ul><li>Ab Method</li><li>BMAD Method (Build More, Architect Dreams)</li><li>claude-code-dev-kit</li><li>claude-code-heavy</li><li>Crystal</li><li>RIPER-5</li><li>SuperClaude</li></ul>
</div>
<div class="facet-card">
<h4>orchestration</h4>
<ul><li>claude-code-by-agents</li><li>Claude Flow</li><li>Claude Squad</li><li>Claude Swarm / SwarmSDK</li><li>MoAI-ADK (Agentic Development Kit)</li><li>systemprompt-orchestrator</li><li>wshobson/agents</li></ul>
</div>
<div class="facet-card">
<h4>project-planning</h4>
<ul><li>BMAD Method (Build More, Architect Dreams)</li><li>NioPD (Nio Product Director)</li></ul>
</div>
<div class="facet-card">
<h4>task-management</h4>
<ul><li>Claude Task Master</li><li>taskmaster-mcp</li></ul>
</div>
</div>

## Adoption Landscape

```mermaid
quadrantChart
    title Complexity vs Community
    x-axis Trivial --> Expert
    y-axis Emerging --> Major
    quadrant-1 Leaders
    quadrant-2 Niche Experts
    quadrant-3 Getting Started
    quadrant-4 Growing
    Ab Method: [0.5, 0.35]
    BMAD Method (Build More, Architect Dreams): [0.5, 0.9]
    CCPM (Claude Code PM): [0.1, 0.1]
    claude-code-by-agents: [0.5, 0.35]
    claude-code-dev-kit: [0.3, 0.35]
    claude-code-heavy: [0.1, 0.1]
    Claude Flow: [0.7, 0.65]
    Claude on Rails: [0.5, 0.35]
    Claude Squad: [0.7, 0.65]
    Claude Swarm / SwarmSDK: [0.7, 0.65]
    Claude Task Master: [0.5, 0.65]
    ClaudeKit: [0.5, 0.35]
    ContextKit: [0.3, 0.35]
    Crystal: [0.3, 0.1]
    MoAI-ADK (Agentic Development Kit): [0.7, 0.65]
    NioPD (Nio Product Director): [0.5, 0.1]
    RIPER-5: [0.3, 0.35]
    Simone: [0.5, 0.35]
    SuperClaude: [0.3, 0.65]
    systemprompt-orchestrator: [0.5, 0.1]
    taskmaster-mcp: [0.5, 0.35]
    wshobson/agents: [0.7, 0.65]
```

## Top Performers

<div class="top-grid">
<div>
<h4>By SOLID Score</h4>
<ol>
<li><strong>claude-code-by-agents</strong> - 4.5/5.0</li>
<li><strong>BMAD Method (Build More, Architect Dreams)</strong> - 4.3/5.0</li>
<li><strong>systemprompt-orchestrator</strong> - 4.3/5.0</li>
<li><strong>claude-code-dev-kit</strong> - 4.2/5.0</li>
<li><strong>Claude Task Master</strong> - 4.2/5.0</li>
</ol>
</div>
<div>
<h4>By Production Ready</h4>
<ol>
<li><strong>BMAD Method (Build More, Architect Dreams)</strong> - 87/100</li>
<li><strong>Claude Task Master</strong> - 83/100</li>
<li><strong>wshobson/agents</strong> - 83/100</li>
<li><strong>ClaudeKit</strong> - 81/100</li>
<li><strong>Claude Swarm / SwarmSDK</strong> - 80/100</li>
</ol>
</div>
</div>

---

<footer class="generation-meta">
<small>Generated: 2025-12-01 11:44 UTC | Template: synthesis.md.j2 v2.0</small>
</footer>

<footer class="signature">∵ RCR Regis ∴</footer>