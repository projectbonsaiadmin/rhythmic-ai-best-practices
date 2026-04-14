# Learnings

Patterns, decisions, and gotchas discovered while building this project. Read this before starting work to avoid repeating solved problems.

<!-- Organize by feature area or technical domain. Each entry should:
     1. Start with a bold summary sentence
     2. Explain both the problem and the solution
     3. Reference commit hashes where helpful
     4. Be added chronologically within its section
-->

## Architecture

<!-- Example entries showing the format: -->

- **Example: CSS variable scoping is the cheapest way to re-theme a component.** When Feature X switched palettes, only the variable definitions needed changes. All 30+ component files using scoped class names picked up the new values automatically. This validates the decision to use scoped CSS variables rather than hardcoded colors.

- **Example: `setTimeout` + React state closures cause stale reads in multi-step flows.** A chained setTimeout callback read state from its closure, but the value was stale because setState is async. Fix: store the value in a `useRef` synchronously and read from the ref in the callback.

## Navigation & UX

<!-- Learnings about navigation patterns, user experience, mobile behavior, etc. -->

## Design & Styling

<!-- Learnings about CSS, theming, responsive design, animations, etc. -->

## Data & Storage

<!-- Learnings about data persistence, API integration, caching, etc. -->

## Performance & Scaling

<!-- Learnings about performance optimization, bundle size, load times, etc. -->
