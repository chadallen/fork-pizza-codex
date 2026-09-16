---
name: start-session
description: Orient a Codex coding session from Git, Beads, session history, and AGENTS.md, then propose work and wait for approval.
---

# Start Session

Orient the session without changing product code. Present a plan and wait for explicit approval before implementation.

## Prerequisites

1. Confirm `bd` is installed. If not, give the installation command and stop.
2. If `.beads/` is absent, run `bd init`. Stop if initialization fails.
3. Run `bd prime` for current workflow guidance.

## Repository state

Read the applicable `AGENTS.md` and `AGENTS.override.md` files. Run `git status` and inspect the five latest commits.

If the working tree contains changes, report them and ask how to proceed. Do not overwrite, stash, or commit work without authorization.

## Session history

List closed `session-log` issues as JSON. Read the newest issue's notes when one exists.

Reuse an existing open `session-log` issue. Otherwise create one for the current date with the `session-log` label. Save its ID for `$end-session`.

On the first session, read `PRD.md` when present and suggest task boundaries. If no product requirements exist, ask the user what they want to build.

## Work state

Inspect ready, blocked, and in-progress Beads issues. Read task descriptions before proposing work. Read only relevant requirement sections when task fields lack context.

Check the repository for documented test, lint, build, and type-check commands. Report missing checks as setup suggestions, not blockers.

## Response

Summarize:

- prior session outcome
- current branch and working-tree state
- active epic progress, if any
- up to three ready tasks
- blockers and human-owned tasks
- available validation commands
- recommended session focus

Wait for approval. After approval, claim the selected task before changing code.
