---
description: Always follow -- minimize context window usage when reading files and searching the codebase
globs: *
---

# Context Window Efficiency

- Prefer targeted reads (`offset` + `limit` parameters) over full file reads. Only read the portion of a file you need. For large files (500+ lines), read the relevant section rather than the entire file.
- Use Explore subagents for multi-file grep-and-report tasks rather than reading files sequentially into the main context. When you need to search across many files or gather information from multiple locations, delegate to an Explore agent and receive a summary.
- When searching for a symbol, pattern, or file, use Grep/Glob directly. Reserve full file reads for when you need to understand surrounding context after finding the target.
