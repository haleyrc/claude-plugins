---
name: go
description: Write high-quality Go code that follows internal and industry best-practices. Use when working with Go files (e.g. go.sum, go.mod, *.go, *_test.go), templ files (*.templ, *_templ.go), or when the user specifically mentions or asks questions about Go itself.
user-invocable: false
---

# Go

This skill defines development patterns, conventions, and preferences for writing, reviewing, and modifying Go code.

## Commands

### Getting documentation

Use the `go doc` CLI for looking up documentation.

For items in the standard library, you can reference packages and their contents directly:
```bash
go doc http              # Returns documentation for the http package
go doc http.Server       # Returns documentation for the Server type
go doc http.Server.Close # Returns documentation for the Close method
```

For third-party code, the package you are querying must already exist in `go.mod` or you will see a "cannot find package error". You must also include the full module path when calling `go doc`:

```bash
go doc github.com/google/uuid            # Returns documentation for the uuid package
go doc github.com/google/uuid.UUID       # Returns documentation for the UUID type
go doc github.com/google/uui.UUID.String # Returns documentation for the String method
```

For local code (code in the current project repository), you can either include the full module path _or_ a relative path:

```bash
# Assuming we are in the `example` project:
go doc github.com/haleyrc/example/lib/log
go doc ./example/lib/log
```

## Additional Documentation

**When working with `templ` code:** See [TEMPL.md](TEMPL.md)
**When working with tests:** See [TESTS.md](TESTS.md)
