# templ

Tools for working with Templ templates.

## Hooks

| Event         | Matcher      | Description                                                                                               |
|---------------|--------------|-----------------------------------------------------------------------------------------------------------|
| `PostToolUse` | `Edit|Write` | Formats all Templ files using `templ fmt` and generates the corresponding Go files with `templ generate`. |
