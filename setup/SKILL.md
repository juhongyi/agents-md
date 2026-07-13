---
name: setup
description: Initialize a Python project with uv using the latest Python 3.13 version supported by uv, then copy juhongyi/skills agents-md/second-level.md to the project-root AGENTS.md. Use when Codex needs to bootstrap or set up a Python project with this standard configuration.
---

# Setup

1. Treat the user-specified target directory as the project root. Use the current directory when no target is specified.
2. Run `uv python install 3.13` to install the latest Python 3.13 version supported by uv.
3. Run `uv init --python 3.13 <project-root>`.
4. Open [agents-md/second-level.md](https://github.com/juhongyi/skills/blob/main/agents-md/second-level.md), read its contents, and copy them to `<project-root>/AGENTS.md`.
