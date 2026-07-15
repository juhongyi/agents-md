---
name: setup
description: Initialize a Python project with uv using the latest Python 3.13 version supported by uv, add the latest stable pytest as a development dependency, ask whether other latest stable libraries are needed, then copy juhongyi/skills agents-md/dev.md to the project-root AGENTS.md. Use when Codex needs to bootstrap or set up a Python project with this standard configuration.
---

# Setup

1. Treat the user-specified target directory as the project root. Use the current directory when no target is specified.
2. Run `uv python install 3.13` to install the latest Python 3.13 version supported by uv.
3. Run `uv init --python 3.13 <project-root>`.
4. Run `uv --directory <project-root> add --dev --prerelease disallow pytest` to add the latest stable pytest as a development dependency.
5. Ask the user whether any additional libraries are needed at their latest stable versions. Add requested libraries with uv, using `--prerelease disallow`.
6. Open [agents-md/dev.md](https://github.com/juhongyi/skills/blob/main/agents-md/dev.md), read its contents, and copy them to `<project-root>/AGENTS.md`.
