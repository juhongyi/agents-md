---
name: loop
description: Orchestrate subagents to implement a requested code change, refactor and verify it, independently review and fix it until no actionable findings remain, then open a ready-for-review pull request. Use when Codex should own a coding task through reviewed PR creation.
---

# Loop

1. Keep the main conversation orchestrator-only: do not perform implementation, refactoring, review, or fix work itself. It may define subagent task boundaries, coordinate and integrate their work, validate results, commit, push, and open the PR.
2. Create every subagent with no inherited user or assistant messages from the main conversation. At creation, ensure the applicable project `AGENTS.md` instructions are present in the subagent's initial context through the same instruction-loading mechanism used for the main agent, independently of conversation history.
3. At the start, create and read a temporary `LOOP_SKILL_MEMORY.md` at the project root for use only while the Loop workflow runs; if it already exists, ask the user before proceeding. Keep it limited to information that implementation and fix subagents must know, update it only when such information exists, and require those subagents to read it before working. Never include it in a review diff, commit, or PR. Require review-only subagents to avoid all access to `LOOP_SKILL_MEMORY.md`.
4. Delegate the scoped implementation and refactoring to an initial implementation subagent: implement only the request, then refactor only changed code without altering behavior.
5. Run the full available test suite.
6. After it passes, create a fresh review-only subagent to independently inspect the request, entire current diff, and repository instructions from scratch with a rigorous, skeptical, and exacting standard, without access to prior review conclusions. Do not let it edit files. Require it to report only well-supported, concrete, actionable findings that identify realistic current or future problems worth fixing; reject speculative, contrived, or feedback-for-feedback's-sake comments. Apply these requirements to every review regardless of sequence. Do not describe any review or verification as "final," "last," or otherwise imply that no further checks may occur.
7. If it reports findings, create a separate fix subagent to address only those concrete findings, refactor only code changed specifically to fix them without altering behavior, and rerun the full suite. Then create a fresh review-only subagent and repeat until no actionable findings remain. Do not set fixed limits on review or verification iterations or on the number of subagents created.
8. Commit only focused changes after a review passes with no actionable findings, push, and open a ready-for-review PR.
9. Ask the user about ambiguity, any relevant conflicting instructions or results, unexpected changes, missing permission, or any error.
