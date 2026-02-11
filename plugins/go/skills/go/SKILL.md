---
name: go
description: General Go development conventions and plugin information. Use when working in Go codebases or needing Go-specific guidance.
user-invocable: false
---

# Plugin Information

The `go` plugin for Claude Code provides a number of utilities for working with Go code.

## Hooks

| Event         | Matcher      | Description                         |
|---------------|--------------|-------------------------------------|
| `PostToolUse` | `Edit|Write` | Formats all Go files using `go fmt` |

## Skills

| Skill                   | Description                                                                                                                                         |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| `go`                    | General Go development conventions and plugin information. Use when working in Go codebases or needing Go-specific guidance.                        |
| `checking-coverage`     | Guidance for checking test coverage in Go. Use when requiring specific information about test coverage for Go files.                                |
| `getting-documentation` | Guidance for obtaining documentation in Go. Use when requiring documentation on Go entities e.g. packages, modules, types, functions, methods, etc. |
