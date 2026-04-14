# Project Name

<!-- One-sentence description -->

**Live site:** <!-- [url](url) -->

## Stack

- **Framework:** <!-- e.g., React 18 + TypeScript + Vite -->
- **Styling:** <!-- e.g., Tailwind CSS 3 -->
- **Components:** <!-- e.g., shadcn/ui (Radix UI primitives) -->
- **Routing:** <!-- e.g., React Router v6 -->
- **State:** <!-- e.g., React Query for async state, localStorage for persistence -->
- **Package manager:** <!-- e.g., bun -->
- **Testing:** <!-- e.g., Vitest + Testing Library -->

## Getting Started

```bash
<!-- install command -->
<!-- dev command + port -->
<!-- build command -->
<!-- test command -->
```

## Architecture

### Layouts

<!-- Describe your layout system. For each layout:
     - What routes it wraps
     - What shared components it includes
     - File path
-->

- **`MainLayout`** (`src/components/MainLayout.tsx`) -- <!-- description -->
- **`AuthLayout`** (`src/components/AuthLayout.tsx`) -- <!-- description -->

### Sitewide Components

- **`Header`** (`src/components/Header.tsx`) -- <!-- description -->
- **`Footer`** (`src/components/Footer.tsx`) -- <!-- description -->

### Routing (defined in `src/App.tsx`)

| Path | Layout | Page Component |
|------|--------|----------------|
| `/` | <!-- layout --> | <!-- component --> |
| <!-- path --> | <!-- layout --> | <!-- component --> |

### Features

<!-- Brief description of each feature/module and what it does -->

## Key Directories

```
src/
+-- components/          # App components
|   +-- ui/              # UI primitives
|   +-- <!-- feature/ -->
+-- pages/               # Route-level page components
+-- data/                # Static data and constants
+-- hooks/               # Custom React hooks
+-- lib/                 # Shared utilities
+-- test/                # Test setup and test files
```

## Design System

Defined in `DESIGN.md`. Key points:

- **Typography:** <!-- font summary -->
- **Colors:** <!-- palette summary -->
- **Layout:** <!-- layout summary -->

## Configuration Files

- `vite.config.ts` -- <!-- description -->
- `tailwind.config.ts` -- <!-- description -->
- `tsconfig.json` -- <!-- description -->
