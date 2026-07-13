---
name: loop
description: Orchestrate subagents to implement a requested code change, refactor and verify it, independently review and fix it until no actionable findings remain, then open a ready-for-review pull request. Use when Codex should own a coding task through reviewed PR creation.
---

# Loop

1. Keep the main conversation orchestrator-only: do not perform implementation, refactoring, review, or fix work itself. It may define subagent task boundaries, coordinate and integrate their work, validate results, commit, push, and open the PR.
2. At the start, ensure `MEMORY.md` exists at the project root and read it before orchestrating. Keep it limited to information that subagents must know, update it only when such information exists, and require every subagent to read it before working.
3. Delegate the scoped implementation and refactoring to an initial implementation subagent: implement only the request, then refactor only changed code without altering behavior.
4. Run the full available test suite.
5. After it passes, create a fresh review-only subagent to independently inspect the request, current diff, and repository instructions. Do not let it edit files; require only concrete actionable findings.
6. If it reports findings, create a separate fix subagent to address only those concrete findings, refactor only code changed specifically to fix them without altering behavior, and rerun the full suite. Then create a fresh review-only subagent and repeat until no actionable findings remain.
7. Commit only focused changes after the final review passes, push, and open a ready-for-review PR.
8. Ask the user about ambiguity, any relevant conflicting instructions or results, unexpected changes, missing permission, or any error.
