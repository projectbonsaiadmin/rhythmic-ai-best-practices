# Project Name -- Design & Style Guide

<!-- This file is the single source of truth for all visual and UI decisions.
     It overrides any conflicting specs in PRDs or other documents. -->

## Typography

| Role | Font | Weight | Usage |
|------|------|--------|-------|
| Titles / Main headings | **<!-- heading font -->** | <!-- weights --> | Hero headlines, page titles, `h1`/`h2` |
| Paragraph / General content | **<!-- body font -->** | <!-- weights --> | Body copy, descriptions, `h3`-`h6` |
| Buttons / Special headers | **<!-- UI font -->** | <!-- weights --> | CTAs, nav labels, section headers, badges |

- <!-- How fonts are loaded (e.g., Google Fonts in index.css, self-hosted, etc.) -->
- Use `font-bold` or `font-semibold` on h1/h2. Default weight at large sizes looks weak.
- Body text must use the primary foreground color, not muted. Reserve muted text for timestamps, captions, and legal copy only.
- h1 should be at least 2.5x body text size. h2 at least 1.75x. Sharp size jumps between levels.
- Limit to 3 text sizes per section: heading, body, caption.

### Feature-Specific Overrides

<!-- If any feature/tool has its own fonts, document them here. Otherwise delete this section. -->

| Feature | Headings | Body | Accent |
|---------|----------|------|--------|
| <!-- Feature name --> | <!-- font --> | <!-- font --> | <!-- font --> |

## Color Palette

### Light Mode

| Token | Value | Usage |
|-------|-------|-------|
| `--background` | <!-- color value --> | Page background |
| `--foreground` | <!-- color value --> | Primary text |
| `--card` | <!-- color value --> | Card surfaces |
| `--primary` | <!-- color value --> | Primary actions |
| `--secondary` | <!-- color value --> | Secondary surfaces |
| `--accent` | <!-- color value --> | Accent highlights |
| `--muted-foreground` | <!-- color value --> | Secondary text only |
| `--border` | <!-- color value --> | Borders and dividers |

### Dark Mode

| Token | Value | Usage |
|-------|-------|-------|
| `--background` | <!-- color value --> | Page background |
| `--foreground` | <!-- color value --> | Primary text |
| `--card` | <!-- color value --> | Card surfaces |
| `--primary` | <!-- color value --> | Primary actions |
| `--accent` | <!-- color value --> | Accent |

<!-- Add any custom tokens specific to your project's brand -->

## Spacing & Layout

- **Grid**: <!-- e.g., 8px increments -->
- **Max content width**: <!-- e.g., max-w-lg (512px) for mobile-first -->
- **Container padding**: <!-- e.g., px-4 -->
- **Section spacing**: <!-- guidance on spacing between sections -->
- **In-app section spacing**: <!-- e.g., space-y-6 or space-y-8 -->
- **Border radius**: <!-- e.g., 0.75rem -->
- **Card padding**: <!-- e.g., p-5 or p-6 -->

## Component Patterns

### Cards
<!-- Document your card pattern. Example: -->
`bg-card border border-border rounded-2xl p-5` with `hover:shadow-md hover:-translate-y-1 transition-all`

### Buttons
- **Primary**: <!-- pattern -->
- **Secondary**: <!-- pattern -->
- **Ghost**: <!-- pattern -->
- Never use generic CTA text ("Get Started," "Sign Up," "Submit"). Use action-specific language.

### Chips, Pills, and Tags
- Selection chips (interactive) must look different from display tags (read-only).
- Let chip width vary by content length. Uniform sizing looks generated.
- Use borders rather than just filled backgrounds. Chips should feel tactile.

### Animations
<!-- Document animation patterns. Example: -->
- Staggered fade-up with ease-out
- Transitions: `transition-colors`, `transition-opacity`, `transition-transform`
- Landing pages: fade-in on scroll per section

## Navigation

- **Header**: <!-- describe header pattern -->
- **In-app bottom nav**: <!-- if applicable -->
- **Every feature should have a visual identity** (icon, illustration, or stylized element)

## Landing Page Structure

<!-- If your project has landing/marketing pages, document the required structure.
     This prevents AI agents from generating generic, template-looking pages. -->

3-5 focused sections. Each section must use a different layout pattern than its neighbors. No two adjacent sections should both be centered.

### 1. Hero (split layout, not centered)
- **Left side**: headline with ONE accent keyword, one-sentence subtitle, CTA button, friction reducer text
- **Right side**: product screenshot, styled output mockup, or contextual illustration. Never text-only.
- Copy should lead with a specific scenario, not a category.

### 2. Interactive Demo / Sample Output (never skip)
- Show realistic results with real-looking data.
- Results must include visual payoff (images, rich cards), not just text listings.

### 3. Credibility (brief)
- Credential-based trust. No fake metrics.

### 4. Final CTA
- Repeat the hero's value prop + CTA button. Do not introduce new concepts here.

## Anti-AI Patterns (Strictly Enforced)

<!-- This section is critical for LLM-assisted development. List patterns that AI agents
     tend to produce that look generic or templated. Customize for your project. -->

**No all-centered stacking.** At least half the sections must use non-centered layout (split columns, offset grids, asymmetric). Three centered sections in a row = stop and restructure.

**No callout chip rows.** Don't place 2-3 phrases in a horizontal badge/pill row. Write a single sentence instead.

**No category title chips.** No badge above the hero that names the category. The headline communicates what the thing is.

**No stacked headings.** No two headings back-to-back without body content between them.

**No text-only pages.** Every landing page needs at least one real image, screenshot, or illustration (not icons or emoji).

**No uniform component styling.** Interactive chips, display tags, primary cards, and secondary cards must not all share identical border-radius/padding/background.

**No washed-out body text.** Body copy uses the primary foreground color, not muted.

**No em dashes.** Use commas, periods, colons, semicolons, or parentheses instead.

<!-- Add project-specific anti-patterns as you discover them -->

## Core Product Pages

**Clear workspace**: One dominant canvas per screen. Users know what to do immediately.

**Stable shell**: Persistent header/tabs, quiet nav. Inner content changes; shell stays fixed.

**Progressive disclosure**: Sparse defaults. Advanced controls behind drawers, accordions, "more" menus.

**State-first**: Design empty, loading, success, error, and disabled states intentionally. Empty states teach the next step.

**Inline interaction**: Edit in place. Inline rename, filters, row expansion, side panels.

**Feedback**: Toasts, inline confirmations, optimistic updates, undo. Subtle, not theatrical.

## Pre-Build Checklist

<!-- Fill in with your project's pre-build requirements. These 20 items cover
     product, visual, brand, content, and functionality dimensions. -->

**Product**: (1) name + tagline, (2) one-sentence description, (3) biggest user outcome, (4) time to complete, (5) requires signup?

**Visual**: (6) accent color, (7) background tone, (8) vibe (warm/clinical/playful), (9) font overrides, (10) logo/icon concept

**Brand**: (11) 3 adjectives for how it should feel, (12) 1-3 admired brands, (13) target audience as a specific person

**Content**: (14) sample output described in detail, (15) credibility angle, (16) friction reducer copy, (17) specific pain-point scenario for lead copy

**Functionality**: (18) try-it-now on landing page or separate?, (19) entry points, (20) what happens after completion?

## Ship-It Checklist

<!-- Customize this checklist for your project. Run through it before marking any
     landing page or major UI as done. -->

- [ ] Nav bar: logo/icon + wordmark + CTA
- [ ] Hero: split layout, accent keyword, subtitle, CTA, friction reducer, visual element
- [ ] At least one real image/illustration/screenshot (not just icons/emoji)
- [ ] Sample output or interactive demo with realistic results and visual payoff
- [ ] No two adjacent sections share the same layout pattern
- [ ] Section spacing varies (not uniform gaps)
- [ ] Body text uses primary foreground color
- [ ] Credibility signal present
- [ ] Final CTA echoes hero value prop (no new concepts)
- [ ] Warm background, no pure white
- [ ] Action-specific CTA copy
- [ ] Mobile responsive
- [ ] Fixed headers and footers do not obscure content beneath them
- [ ] Footer: copyright + legal links
- [ ] Copy uses specific details, not polished generalities

## Design Principles

<!-- 5-8 principles that guide all design decisions. These should be opinionated
     and specific to your project's aesthetic, not generic "good design" advice. -->

1. **<!-- Principle 1 -->**: <!-- description -->
2. **<!-- Principle 2 -->**: <!-- description -->
3. **<!-- Principle 3 -->**: <!-- description -->
4. **<!-- Principle 4 -->**: <!-- description -->
5. **<!-- Principle 5 -->**: <!-- description -->
