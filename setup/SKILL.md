---
name: setup
description: Initialize a Python project with uv using the latest stable CPython 3.13.x release, then copy juhongyi/skills agents-md/second-level.md to the project-root AGENTS.md. Use when Codex needs to bootstrap or set up a Python project with this standard configuration.
---

# Setup

1. Treat the user-specified target directory as the project root. Use the current directory when no target is specified.
2. Find the latest stable CPython 3.13.x release on the official [Python downloads page](https://www.python.org/downloads/). Exclude prereleases and do not select another minor version.
3. Run `uv init --python <latest-3.13.x> <project-root>` with the exact release number.
4. Download [agents-md/second-level.md](https://raw.githubusercontent.com/juhongyi/skills/main/agents-md/second-level.md) to a temporary file, then move it to `<project-root>/AGENTS.md` so its contents are copied exactly.
5. Verify that `<project-root>/.python-version` contains the selected release and that `<project-root>/AGENTS.md` matches the downloaded source.
