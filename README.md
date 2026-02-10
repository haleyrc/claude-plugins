# Personal Plugins for Claude

This is a set of personalized plugins that I use in Claude Code. I make no claim about the broader applicability of the content in this repository, so use at your own risk.

## Installation

From a Claude session in your project:

```bash
/plugin marketplace add git@github.com:haleyrc/claude-plugins.git
```

## Structure

```
claude-plugins/
├── .claude-plugin/marketplace.json    # Plugin registry
└── plugins/                           # Plugin configuration
```

## Available Plugins

|                                                      |                                                  |
|------------------------------------------------------|--------------------------------------------------|
| [`go`](./plugins/go/README.md)                       | Tools for working with Go                        |
| [`output-styles`](./plugins/output-styles/README.md) | Output styles for customizing Claude's responses |
