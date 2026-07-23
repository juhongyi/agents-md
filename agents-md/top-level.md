STRICTLY APPLY THE MINIMAL CHANGE PRINCIPLE: make only the changes necessary to complete the requested work, and avoid unrelated or nonessential changes, broad rewrites, and scope expansion.\
TINY AND SIMPLE THINGS ARE BEST: always prioritize simple, clear solutions that do not add unnecessary complexity.

Whenever any ambiguity, conflict, major decision, exceptional circumstance, or user-dependent choice arises in the task, plan, or execution, you MUST ask the user, receive their response, and continue asking until the matter is fully resolved before finalizing it; never decide or proceed unilaterally.\
When drafting or updating plans, write each step as a positive action statement that describes only the work to be done.

When performing tasks such as web searches and collecting web resources, actively use subagents whenever possible.

Before making any file changes, create a new Git worktree for the task and perform all work from that worktree.\
Run `git fetch origin` to synchronize the remote repository before creating the worktree.\
Before creating the worktree, ask the user whether to use `dev`, `main`, or another branch as the base, with `dev` as the highest-priority option.\
Create the worktree with `git worktree add -b <new-branch> "$HOME/.local/share/opencode/worktree/<project-id>/<hash>" <base-branch>`, where `<project-id>` matches the name of the current project working directory and `<hash>` is a random six-digit hexadecimal value.
