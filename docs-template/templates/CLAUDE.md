# Project Name

<!-- One-sentence description of what this project is -->

## Project Overview

- **URL**: <!-- production URL -->
- **Stack**: <!-- e.g., React + TypeScript + Vite, Tailwind CSS, shadcn/ui -->
- **Package manager**: <!-- e.g., bun, npm, pnpm -->
- **Routing**: <!-- e.g., React Router v6, Next.js App Router, file-based -->

## Architecture

<!-- 2-3 paragraphs describing the high-level architecture. Cover:
  - How the app is organized (monorepo? single package? microservices?)
  - Key architectural patterns (e.g., each feature at its own route, shared design system)
  - What each feature/module owns (its own data, components, logic, etc.)
-->

### Routing Convention

<!-- Document your URL structure pattern. Examples:
  - `/<feature>` — The core product page
  - `/api/<resource>` — API endpoints
  - `/admin/<section>` — Admin pages
-->

### Layouts

<!-- Document your layout hierarchy. For each layout, note:
  - What routes it wraps
  - What shared components it includes (header, footer, sidebar)
  - Any special behavior (sticky nav, bottom tabs, etc.)
-->

### Sitewide Components

<!-- List components that appear on every page and their responsibilities.
  - Header — what it contains, where it lives
  - Footer — what it contains, legal links, etc.
  - Sidebar — if applicable
-->

## Current State

<!-- Table of features/modules with their status. Keep this current. -->

| Feature | Route | Backend | Key Details |
|---------|-------|---------|-------------|
| <!-- Feature 1 --> | <!-- /route --> | <!-- backend tech --> | <!-- brief description --> |
| <!-- Feature 2 --> | <!-- /route --> | <!-- backend tech --> | <!-- brief description --> |

## Development

```bash
# Install dependencies
<!-- package manager install command -->

# Start dev server
<!-- dev command -->

# Build for production
<!-- build command -->

# Run tests
<!-- test command -->
```

## Finding Files

Use glob/grep to find files. The codebase follows consistent naming conventions:

<!-- Document your file naming conventions. Examples: -->
- **Feature components**: `src/components/<feature-name>/`
- **Pages**: `src/pages/<FeatureName>.tsx`
- **Feature logic**: `src/lib/<feature-name>-*.ts`
- **Feature data**: `src/data/<feature-name>/`
- **Shared libs**: `src/lib/utils.ts`, `src/lib/api.ts`
- **Tests**: `src/test/*.test.ts`
- **Specs/docs**: `docs/`

### Key Documentation

| File | Purpose |
|------|---------|
| `CLAUDE.md` | This file. Architecture and conventions |
| `DESIGN.md` | Typography, colors, spacing, component patterns |
| `TODO.md` | Task tracking by priority |
| `LEARNINGS.md` | Technical gotchas and patterns from past sessions |
| `SHIFT_CHART.md` | Current project state (read at session start, update at session end) |
| `DECISIONS.md` | Date-stamped product and architecture decision log |
| `TESTS.md` | Test suite inventory, status, and conventions |

## Session Protocol

Behavioral rules for all LLM agents are defined in `.claude/rules/`. These apply automatically for Claude Code. The rules are:

1. **Before coding**: Read relevant docs, check TODO.md/LEARNINGS.md/SHIFT_CHART.md/DECISIONS.md, understand the design system.
2. **After completing work**: Update LEARNINGS.md, TODO.md, SHIFT_CHART.md, and DECISIONS.md as appropriate.
3. **Always**: Follow `DESIGN.md` exactly. Leave docs better than you found them.
4. **Planning**: Include a confidence rating (1-10) and "questions for lead engineer" section for large tasks.

## Multi-Agent Coordination

<!-- If multiple agents or developers work on this codebase, document:
  - Who does what (which agent handles backend vs frontend vs infrastructure)
  - Branch/commit strategy per agent
  - How to avoid conflicts (check SHIFT_CHART before starting)
  - What to do if you break something another agent built
-->

This codebase has multiple contributors:

- **Claude Code** -- Uses feature branches with pull requests. Handles <!-- scope: e.g., backend, infrastructure, API integration -->.
- **<!-- Other agent/developer -->** -- <!-- commit strategy -->. Handles <!-- scope -->.
- **Human** -- Merges PRs, writes specs, makes product decisions.

Before starting work, check `SHIFT_CHART.md` to see what other agents are actively building. If another agent is mid-build on a feature, avoid modifying that feature's files unless asked.
