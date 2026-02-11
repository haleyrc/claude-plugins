---
name: templ
description: General Templ development conventions and plugin information. Use when working in Go codebases containing Templ files (*.templ,*.templ.go) or needing Templ-specific guidance.
user-invocable: false
---

# Plugin Information

The `templ` plugin for Claude Code provides a number of utilities for working with Templ templates.

## Hooks

| Event         | Matcher      | Description                                                                                               |
|---------------|--------------|-----------------------------------------------------------------------------------------------------------|
| `PostToolUse` | `Edit|Write` | Formats all Templ files using `templ fmt` and generates the corresponding Go files with `templ generate`. |
