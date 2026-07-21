---
name: refactor
description: Refactor existing code according to explicit user requirements while preserving behavior except for changes the user specifically requests. Use when the user explicitly invokes `$refactor` or asks to refactor, restructure, simplify, clean up, or improve existing code without unintended behavior changes.
---

# Refactor

1. Read applicable project instructions and inspect the requested code, tests, and relevant call sites.
2. Base the scope and intended behavior on the user's explicit requirements.
3. Ask the user before proceeding when the request, intended behavior, scope, or applicable instructions are ambiguous or conflicting.
4. Refactor only the requested scope. Make the smallest clear change that satisfies the request, and avoid unrelated cleanup or broad rewrites.
5. Preserve existing behavior unless the user explicitly requests a behavior change.
6. Treat only explicit user requirements, never the current diff itself, as candidates for durable project guidance.
7. Update only an existing `AGENTS.md` at the target project root, and only when a requirement is clearly important, durable, reusable, and expressible generally. Write any update as general guidance, and avoid case-specific micromanagement. Skip temporary or narrow requirements. Do not create an `AGENTS.md` when none exists. Ask the user when a requirement's importance or generality is ambiguous.
8. Run relevant tests and checks, then inspect every resulting change, including new or untracked files, for unintended behavior or out-of-scope changes.
