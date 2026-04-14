# Decisions

Product and architecture decisions with rationale. Before changing something fundamental, check here first.

## How to Use This File

- **Before changing architecture**: Search this file for keywords related to what you're changing.
- **After making a decision**: Add a new entry at the top of the relevant section with the date and 2-3 sentences of reasoning.
- **Format**: `**YYYY-MM-DD: Decision title.** Rationale in 2-3 sentences.`

## Architecture

<!-- Example entries showing the format: -->

**YYYY-MM-DD: Example -- chose localStorage over a database for MVP.** No signup friction, instant load, zero backend cost. Users lose data on browser clear, acceptable for a tool that generates fresh output each session. Migrate to a database when persistence becomes a user request.

**YYYY-MM-DD: Example -- direct API calls from browser, no server proxy.** The API key is exposed in the browser bundle, acceptable for MVP with rate limiting. A server-side proxy is the production approach. This decision should be revisited before public launch.

## Design

<!-- Design decisions that override defaults or PRD specs. Example: -->

**YYYY-MM-DD: Example -- DESIGN.md overrides PRD typography specs.** Multiple PRDs specified custom fonts. DESIGN.md is the single source of truth. Only features with strong brand identity get font overrides.

## Process

<!-- Team process decisions. Example: -->

**YYYY-MM-DD: Example -- no CI pipeline for MVP.** The team is small. Manual testing is sufficient for now. CI should be added before public launch or when direct-to-main commits become a quality problem.
