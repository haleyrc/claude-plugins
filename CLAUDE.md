# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A personal collection of Claude Code plugins, published as a marketplace package (`haley-claude`). Plugins provide skills (specialized capabilities) and output styles for use within Claude Code sessions.

## Repository Layout

- `.claude-plugin/marketplace.json` — Central registry that defines all available plugins with name, version, source path, and strict mode setting.
- `plugins/<plugin-name>/` — Each plugin directory contains a `README.md` and its content (skills or output styles).
- Skills are defined in markdown files (e.g. `SKILL.md`, `TEMPL.md`, `TESTS.md`) with YAML frontmatter.
- Output styles are standalone markdown files describing voice/tone behavior.

## How It Works

There is no build step, no dependencies, and no tests. This is a pure documentation/configuration repository. All content is markdown consumed directly by Claude Code at runtime.

To install from a Claude session: `/plugin marketplace add git@github.com:haleyrc/claude-plugins.git`

## Adding a Plugin

1. Create a new directory under `plugins/`.
2. Add a `README.md` describing the plugin.
3. Add skill or output-style markdown files as needed.
4. Register the plugin in `.claude-plugin/marketplace.json` by adding an entry to the `plugins` array with `name`, `description`, `version`, `source`, and `strict` fields.

## Conventions

- Plugin versions track independently but currently all sit at `0.0.1`.
- All plugins use `strict: false`.
- Skill markdown files use YAML frontmatter to declare metadata (e.g. whether the skill is user-invocable).
