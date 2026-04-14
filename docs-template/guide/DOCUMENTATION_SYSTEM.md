# How the Documentation System Works

This guide explains the documentation system extracted from rhythmic-tools-v2 -- a project built over months with multiple LLM agents (Claude Code, Lovable) and human developers collaborating on the same codebase. The system evolved to solve real coordination problems: agents repeating solved bugs, overriding deliberate decisions, conflicting with each other's work, and producing generic AI-looking output.

The system is not just a collection of files. It's a protocol -- a set of interlocking practices that keep the project coherent across sessions and agents.

---

## The File Hierarchy

Each file has a specific authority level and purpose. The hierarchy matters because agents need to know which document wins when two sources conflict.

```
DESIGN.md          (highest authority for visual/UI decisions)
   |
CLAUDE.md          (highest authority for architecture/conventions)
   |
DECISIONS.md       (explains "why" -- prevents undoing deliberate choices)
   |
Feature Specs/PRDs (feature-specific requirements, subordinate to DESIGN.md)
   |
LEARNINGS.md       (accumulated knowledge -- prevents repeating mistakes)
   |
SHIFT_CHART.md     (current state -- prevents conflicts between agents)
   |
TODO.md            (task tracking -- prevents duplicate effort)
   |
TESTS.md           (test inventory -- prevents untested changes)
```

**Authority rule**: If a PRD says "use Inter font" but DESIGN.md says "use Merriweather for body text," DESIGN.md wins. The only way to override DESIGN.md is a human decision recorded in DECISIONS.md.

---

## The Three Protocols

### 1. Pre-Coding Protocol (`.claude/rules/read-docs-before-coding.md`)

Before writing any code, agents must read:

1. **CLAUDE.md** -- understand the architecture
2. **DESIGN.md** -- understand the visual system
3. **Feature spec** -- understand what to build
4. **TODO.md** -- check if the task is already tracked
5. **LEARNINGS.md** -- don't repeat solved problems
6. **SHIFT_CHART.md** -- don't conflict with other agents
7. **DECISIONS.md** -- don't override deliberate choices

This reading order is intentional. Architecture and design come first (they constrain everything), then feature details, then awareness of the project's current state.

### 2. Post-Task Protocol (`.claude/rules/update-docs-after-task.md`)

After completing work, agents must update up to 5 files:

1. **LEARNINGS.md** -- non-obvious discoveries
2. **TODO.md** -- unfinished work and follow-ups
3. **SHIFT_CHART.md** -- current state, risks, confidence
4. **DECISIONS.md** -- product/architecture choices worth recording
5. **CLAUDE.md / DESIGN.md / README.md** -- if fundamentals changed

This is what keeps the system alive. Without post-task updates, the docs decay within a few sessions.

### 3. The Kaizen Principle (`.claude/rules/kaizen.md`)

Every session should leave documentation a little better than it found it. A clarified sentence, a stale entry updated, a missing detail added. Small improvements compound.

This is not about writing new docs -- it's about maintenance. The system works because agents are required to maintain it as they go.

---

## Multi-Agent Coordination

The documentation system solves three coordination problems:

### Problem 1: Agents don't know what other agents are doing
**Solution**: `SHIFT_CHART.md` -- read at session start, updated at session end. Contains current state of every feature, open questions, active risks, and a confidence rating.

### Problem 2: Agents undo deliberate decisions
**Solution**: `DECISIONS.md` -- date-stamped entries with rationale. When an agent sees something that looks "wrong" and wants to "fix" it, they check DECISIONS.md first. If there's an entry explaining why it's that way, they leave it alone (or discuss with the human lead).

### Problem 3: Agents repeat solved problems
**Solution**: `LEARNINGS.md` -- searchable by keyword. Before debugging a tricky issue, agents check if a solution was already found in a previous session.

### Agent-Specific Instructions

Each non-primary agent gets its own instruction file (e.g., `LOVABLE.md`) that documents:
- What to read before starting
- Design system compliance rules
- Shared patterns to reuse (don't reinvent)
- Commit discipline with good/bad examples
- **What the agent cannot do** (explicit constraints prevent wasted attempts)
- Post-task update requirements
- How to coordinate with other agents

---

## The Anti-AI Patterns Section

One of the most valuable parts of DESIGN.md is the "Anti-AI Patterns" section. LLM agents tend to produce recognizable output patterns: all-centered layouts, badge/chip rows, em dashes, generic CTA text, uniform component styling. The Anti-AI Patterns section explicitly lists these tendencies and bans them.

This section should be customized for your project. Start with the defaults in the template, then add patterns you notice your agents producing that look generic or templated.

---

## The Checklists

Two checklists in DESIGN.md catch common omissions:

### Pre-Build Checklist (20 items)
Run before starting a new feature. Covers product definition, visual identity, brand voice, content requirements, and functionality decisions. Prevents building without a clear direction.

### Ship-It Checklist (15 items)
Run before marking a feature as done. Covers navigation, hero layout, real images, sample output, responsive behavior, legal links, and copy quality. Prevents shipping half-finished pages.

---

## How to Adopt This System

### Step 1: Copy the files
Copy `templates/` contents to your repo root, `claude-rules/` to `.claude/rules/`. Rename `PROJECT_README.md` to `README.md`.

### Step 2: Fill in CLAUDE.md first
This is your master architecture doc. Fill in the project overview, routing conventions, file structure, and current state. Everything else references this file.

### Step 3: Fill in DESIGN.md
Define your typography, colors, spacing, and component patterns. Even if your design system is minimal, having it written down prevents agents from inventing their own.

### Step 4: Seed the living docs
Add 1-2 entries to DECISIONS.md (your most important architectural choices), LEARNINGS.md (your biggest gotcha), and SHIFT_CHART.md (current project state). These files grow organically after that.

### Step 5: Customize Anti-AI Patterns
Review the default patterns in DESIGN.md. Remove any that don't apply to your project. Add patterns specific to your stack or aesthetic.

### Step 6: The system maintains itself
With the Claude rules in place, agents will read before coding and update after completing work. The Kaizen principle ensures gradual improvement. You just need to review the docs occasionally to prune stale entries.

---

## What Makes This System Work

1. **It's interlocking.** Each file references others. CLAUDE.md points to DESIGN.md. Rules point to LEARNINGS.md and DECISIONS.md. No file exists in isolation.

2. **It has clear authority.** When docs conflict, there's an explicit winner. This prevents agents from picking whichever source supports their preferred approach.

3. **It's maintained by the agents that use it.** The post-task protocol and Kaizen principle mean the docs stay current without human intervention.

4. **It's opinionated.** The Anti-AI Patterns section and Ship-It Checklist enforce specific quality standards. Vague guidelines get ignored; specific rules get followed.

5. **It acknowledges constraints.** The "What X Cannot Do" section in agent instruction files prevents wasted effort and broken builds from agents attempting tasks outside their capabilities.
