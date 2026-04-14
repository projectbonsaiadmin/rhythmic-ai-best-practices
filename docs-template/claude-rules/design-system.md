---
description: Always follow -- DESIGN.md is the single source of truth for all UI work
globs: "src/**/*.{tsx,css,ts}"
---

# Design System

`DESIGN.md` is the single source of truth for typography, colors, spacing, component patterns, and landing page structure. Follow it exactly.

- Typography: Use the fonts specified in DESIGN.md. Check for feature-specific overrides before assuming defaults.
- Colors: Use CSS variable tokens, never hardcoded hex/HSL. Each feature scopes its palette via a class wrapper.
- Landing pages must follow the Landing Page Structure and Ship-It Checklist in DESIGN.md.
- Anti-AI patterns are strictly enforced (review the full list in DESIGN.md before building any UI).
