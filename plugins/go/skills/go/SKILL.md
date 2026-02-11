---
name: go
description: Write high-quality Go code that follows internal and industry best-practices. Use when working with Go files (e.g. go.sum, go.mod, *.go, *_test.go), templ files (*.templ, *_templ.go), or when the user specifically mentions or asks questions about Go itself.
user-invocable: false
---

This skill defines development patterns, conventions, and preferences for writing, reviewing, and modifying Go code.

## Getting documentation

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

## Test Coverage

Before reading files to determine testing gaps, use `go test --cover` to verify test coverage.

**For a quick summary:**

```bash
go test --cover ./...             # Generate coverage for every package in the project
go test --cover ./example/lib/log # Generate coverage numbers for a specific package
go test --cover ./example/lib/... # Generate coverage numbers for a package and all its sub-packages
```

This generates lines indicating the test status, package name, test run time, and percentage of statements covered. For example:

```bash
ok      github.com/example/lib/assert   1.146s  coverage: 83.1% of statements
```

**For detailed coverage information:**

```bash
go test --coverprofile=c.out <package selector> # Generate a coverage profile
go tool cover --func=c.out                      # Output per-function coverage
rm c.out                                        # Clean up once the profile is no longer required
```

This will produce lines indicating the path to the file, the line number of the function-under-test, the name of the function, and the coverage percentage. For example:

```bash
github.com/haleyrc/lib/assert/assert.go:20:             ContentType             100.0%
```

## Additional Documentation

**When working with `templ` code:** See [TEMPL.md](TEMPL.md)
**When working with tests:** See [TESTS.md](TESTS.md)
