# Rhythmic AI Best Practices

A battle-tested documentation system for building software with AI agents, extracted from a production codebase built with Claude Code, Lovable, and human developers over several months.

When multiple AI agents share a codebase, three things break fast:

1. **Agents repeat solved problems** -- they hit the same bug you fixed two sessions ago
2. **Agents undo deliberate decisions** -- they "improve" code that was built a specific way on purpose
3. **Agents step on each other** -- two agents edit the same files and create merge conflicts

This repo contains the documentation system, Claude Code rules, and markdown templates that solved these problems for us. It's designed to be forked or copied into any project.

## Who This Is For

- Teams using **Claude Code**, **Lovable**, **Codex**, **Cursor**, or other AI coding agents
- Solo developers who use AI agents across multiple sessions and want continuity
- Anyone tired of AI agents producing generic, template-looking output

## How to Use This Repo

### Option 1: Fork it

Fork this repo and customize the templates for your project. The structure is ready to go -- just fill in your project-specific details.

### Option 2: Copy what you need

Clone or download, then work from the portable kit in `docs-template/`:

```bash
# Clone the repo
git clone https://github.com/projectbonsaiadmin/rhythmic-ai-best-practices.git
cd rhythmic-ai-best-practices/docs-template

# Copy templates to your project root
cp templates/CLAUDE.md /path/to/your/project/CLAUDE.md
cp templates/DESIGN.md /path/to/your/project/DESIGN.md
cp templates/DECISIONS.md /path/to/your/project/DECISIONS.md
cp templates/LEARNINGS.md /path/to/your/project/LEARNINGS.md
cp templates/SHIFT_CHART.md /path/to/your/project/SHIFT_CHART.md
cp templates/TODO.md /path/to/your/project/TODO.md
cp templates/TESTS.md /path/to/your/project/TESTS.md
cp templates/PROJECT_README.md /path/to/your/project/README.md

# Copy Claude Code rules
mkdir -p /path/to/your/project/.claude/rules
cp claude-rules/*.md /path/to/your/project/.claude/rules/

# If you have a secondary AI agent (Lovable, Cursor, etc.)
cp templates/LOVABLE.md /path/to/your/project/AGENT_NAME.md
```

### Getting Started After Copying

1. **Fill in `CLAUDE.md` first** -- this is your master architecture doc. Add your project overview, stack, routing conventions, and file naming patterns. Everything else references this file.

2. **Fill in `DESIGN.md`** -- define your typography, colors, spacing, and component patterns. Even a minimal design system prevents agents from inventing their own styles.

3. **Seed the living docs** -- add 2-3 entries to `DECISIONS.md` (your most important architectural choices), one entry to `LEARNINGS.md` (your biggest gotcha), and fill in `SHIFT_CHART.md` with current project state.

4. **Customize Anti-AI Patterns** -- review the patterns in `DESIGN.md` and adjust for your project. These prevent AI agents from producing generic, obviously-AI-generated output.

5. **The system maintains itself** -- with the Claude rules in `.claude/rules/`, agents will automatically read docs before coding and update docs after completing work.

## What's in This Repo

```
rhythmic-ai-best-practices/
+-- docs-template/                     # Portable kit to copy into your own repo
|   +-- templates/                    # Drop-in markdown templates for your repo root
|   |   +-- CLAUDE.md                 # Architecture & conventions (master doc)
|   |   +-- DESIGN.md                 # Design system (visual authority)
|   |   +-- DECISIONS.md              # Decision log with rationale
|   |   +-- LEARNINGS.md              # Technical gotchas and patterns
|   |   +-- SHIFT_CHART.md            # Cross-session state handoff
|   |   +-- TODO.md                   # Prioritized task tracking
|   |   +-- TESTS.md                  # Test inventory and conventions
|   |   +-- LOVABLE.md                # Secondary agent instructions
|   |   +-- PROJECT_README.md         # Project README template
|   +-- claude-rules/                 # Copy to .claude/rules/ in your project
|   |   +-- kaizen.md                 # Leave docs better than you found them
|   |   +-- update-docs-after-task.md # Post-task documentation protocol
|   |   +-- read-docs-before-coding.md # Pre-coding reading checklist
|   |   +-- design-system.md          # DESIGN.md compliance enforcement
|   |   +-- context-efficiency.md     # Context window usage optimization
|   +-- guide/
|       +-- DOCUMENTATION_SYSTEM.md   # Deep dive: how and why the system works
```

## The Documentation Hierarchy

Each file has a specific authority level. When two sources conflict, the higher-authority file wins.

| File | Authority | What It Does |
|------|-----------|--------------|
| **DESIGN.md** | Highest (visual) | Single source of truth for all UI/design decisions |
| **CLAUDE.md** | Highest (architecture) | Master reference for architecture, conventions, file structure |
| **DECISIONS.md** | High | Date-stamped rationale prevents agents from undoing deliberate choices |
| **LEARNINGS.md** | Reference | Accumulated gotchas prevent agents from repeating solved problems |
| **SHIFT_CHART.md** | Current state | Cross-session handoff prevents agent conflicts |
| **TODO.md** | Task tracking | Prioritized backlog prevents duplicate effort |
| **TESTS.md** | Reference | Test inventory, status, and conventions |
| **LOVABLE.md** | Agent-specific | Instructions and constraints for secondary AI agents |

## The Claude Code Rules

These 5 files go in `.claude/rules/` and are automatically enforced by Claude Code:

| Rule | What It Does |
|------|-------------|
| **kaizen.md** | Agents improve docs incrementally every session |
| **update-docs-after-task.md** | Agents update 5 files after completing work (LEARNINGS, TODO, SHIFT_CHART, DECISIONS, and master docs) |
| **read-docs-before-coding.md** | Agents read 8 docs before writing any code |
| **design-system.md** | Enforces DESIGN.md as the visual authority for all UI work |
| **context-efficiency.md** | Agents use targeted file reads to minimize context window usage |

## Key Concepts

### The Three Protocols

**Pre-coding**: Read CLAUDE.md, DESIGN.md, the feature spec, TODO, LEARNINGS, SHIFT_CHART, and DECISIONS -- in that order. Architecture first, then awareness of current state.

**Post-task**: Update LEARNINGS (gotchas found), TODO (follow-ups), SHIFT_CHART (what you shipped, new risks), DECISIONS (choices made), and master docs if fundamentals changed.

**Kaizen**: Every session leaves docs a little better. A clarified sentence, a stale entry updated, a missing detail added. Small improvements compound.

### Anti-AI Patterns

DESIGN.md includes an "Anti-AI Patterns" section that explicitly bans output patterns LLM agents tend to produce: all-centered layouts, badge/chip rows, em dashes, generic CTA text, uniform component styling. Customize this list for your project and stack.

### Multi-Agent Coordination

The system supports multiple agents (Claude Code, Lovable, Cursor, human developers) working on the same codebase. `SHIFT_CHART.md` is the handoff note -- read at session start, updated at session end. Each non-primary agent gets its own instruction file (e.g., `LOVABLE.md`) documenting its capabilities, constraints, and coordination rules.

## Customization Guide

### Must customize for your project
- **CLAUDE.md**: Project overview, architecture, routing, file conventions
- **DESIGN.md**: Typography, colors, component patterns, Anti-AI patterns, checklists
- **LOVABLE.md**: Agent name, capabilities, constraints, shared patterns

### Works out of the box
- **DECISIONS.md**: Generic format; just add your entries
- **LEARNINGS.md**: Generic format; just add your entries
- **SHIFT_CHART.md**: Generic sections; just fill in current state
- **TODO.md**: Generic priority structure; just add tasks
- **All 5 Claude rules**: Project-agnostic, ready to use

### Optional
- **TESTS.md**: Skip if you don't have a test suite yet
- **LOVABLE.md**: Skip if you're not using a secondary AI agent

## Learn More

Read [`docs-template/guide/DOCUMENTATION_SYSTEM.md`](docs-template/guide/DOCUMENTATION_SYSTEM.md) for a deep dive into how the system works, why each file exists, the authority hierarchy, and what makes it effective.

## Contributing

Found a pattern that works well? Open an issue or PR. This system evolved from real production use -- contributions from other multi-agent workflows are welcome.

## License

MIT
