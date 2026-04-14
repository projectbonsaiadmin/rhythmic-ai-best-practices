# Secondary Agent Instructions

<!-- Rename this file to match your secondary agent (e.g., LOVABLE.md, CURSOR.md, COPILOT.md).
     This file provides agent-specific instructions for any LLM agent that is NOT Claude Code
     but commits code to this repository. -->

You are part of a multi-agent team building <!-- project name -->. Claude Code, human developers, and you share this repository. <!-- Describe commit strategy, e.g., "Your commits go directly to main" or "You work on feature branches" -->.

## Before Starting Any Task

1. **Read `CLAUDE.md`** (full file). It defines the architecture, routing conventions, file structure, and rules that apply to ALL agents including you.
2. **Read `DESIGN.md`** (full file). It is the single source of truth for typography, colors, spacing, component patterns, and landing page structure. Follow it exactly.
3. **Read the spec** for the feature you're working on (in `docs/`).
4. **Read `SHIFT_CHART.md`** to understand what just shipped, what's risky, and what other agents are working on. Avoid conflicts.
5. **Read `DECISIONS.md`** to understand why things are the way they are. Do not "improve" a deliberate decision without discussing it with the human lead first.
6. **Read `LEARNINGS.md`** for technical gotchas specific to your feature.
7. If the task involves a specific feature, read its layout file and main component.

## Design System Compliance

`DESIGN.md` is authoritative. These are the rules most likely to be missed:

### Typography
<!-- List your project's font rules here -->

### Colors
- Use CSS variable tokens, never hardcoded hex or HSL values.
- <!-- Add project-specific color rules -->

### Landing Pages
Must follow `DESIGN.md` Landing Page Structure.

### Anti-AI Patterns (Strictly Enforced)
<!-- Copy the Anti-AI Patterns section from DESIGN.md or reference it -->
- Review the Anti-AI Patterns section in DESIGN.md before building any UI.

### Ship-It Checklist
Before marking any landing page or major UI as done, run through the Ship-It Checklist in `DESIGN.md`.

## Shared Patterns to Reuse

Do not reinvent these. They already exist and work:

<!-- List your project's reusable patterns. Examples: -->
- **Layout wrapper**: <!-- e.g., Use `ToolShell` for new layouts -->
- **CSS variable scoping**: <!-- e.g., Create a `.feature-name` class in index.css -->
- **Analytics**: <!-- e.g., Use `createTracker(prefix)` -->
- **Rate limiting**: <!-- e.g., Use `createRateLimiter(key, limit)` -->
- **Storage**: <!-- e.g., Use `getStoredValue`/`setStoredValue` for localStorage -->
- **Error boundaries**: <!-- e.g., Already included in layout wrapper -->

## Commit Discipline

<!-- Describe your commit strategy and provide examples of good/bad messages -->

**Bad commit messages** (avoid these):
- "Changes"
- "Work in progress"
- "Save plan"

**Good commit messages:**
- "Add Groups tab with card grid and create form"
- "Wire values flow into main tab with persistence"
- "Fix header sticky position and accent color"

**Format**: `<Verb> <scope>: <what changed>`. If saving intermediate progress, use `WIP: <specific description>`.

Do not commit:
- Build artifacts, `.env` files, or API keys
- Files outside your task scope

## What This Agent Cannot Do

<!-- Be explicit about constraints. This prevents the agent from attempting tasks
     that will fail, wasting time and potentially breaking things. -->

Acknowledge these constraints. Do not attempt these tasks; instead document the need:

- <!-- e.g., Run CLI commands (test, build, deploy). Note the need in TODO.md. -->
- <!-- e.g., Create branches or PRs. -->
- <!-- e.g., Run the test suite. -->
- <!-- e.g., Access .env or environment variables at edit time. -->
- <!-- e.g., Modify shared infrastructure files. -->

## After Completing a Task

1. **Update `LEARNINGS.md`** if you discovered something non-obvious.
2. **Update `TODO.md`** if your task surfaced unfinished work or follow-ups.
3. **Update `SHIFT_CHART.md`**: Change "Current State" to reflect what you shipped. If another agent needs to follow up, add it to "Open Questions" or "Active Risks."
4. **Update `CLAUDE.md`** if you created new files or directories that other agents need to know about.

## Coordination with Other Agents

- **Claude Code works on feature branches** and submits PRs. If a PR is open on a feature you're working on, do not modify the same files.
- **Check `SHIFT_CHART.md`** before starting.
- **Infrastructure is Claude Code's domain**. If you need backend changes, describe the need in `TODO.md` and `SHIFT_CHART.md`.
- **If you break something another agent built**, note the breakage and your fix in your commit message. Update `SHIFT_CHART.md`.

## The Kaizen Principle

Every session should leave the documentation a little better than it found it. A clarified sentence, a missing file path added, a new learning captured. Small improvements compound.
