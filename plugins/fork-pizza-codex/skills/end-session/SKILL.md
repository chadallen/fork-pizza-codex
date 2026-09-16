---
name: end-session
description: Close a Codex coding session by verifying work, recording the Beads session log, committing intended changes, syncing Beads, and pushing Git.
---

# End Session

Finish the session completely. Work is not complete until the intended commits and Beads state are pushed.

## Audit

Run `bd prime`, read applicable `AGENTS.md` files, and inspect:

- `git status`
- branch and upstream state
- commits created during the session
- open, in-progress, blocked, and ready Beads issues
- the open issue labeled `session-log`

Identify unfinished work. Create or update Beads issues for follow-up instead of leaving untracked promises in chat.

## Verify

Run the repository's required tests, lint, build, and type checks for the session's changes. Fix in-scope failures. Record external or deferred failures in Beads.

Review changed `AGENTS.md` files for stale commands or conflicting instructions. Ask before making instruction changes that were not part of the session.

## Record the session

Update the open `session-log` issue with:

- completed work and task IDs
- validation performed
- remaining tasks and blockers
- branch and commit state
- the recommended next action

Close the session-log issue after its notes are complete.

## Commit and push

Stage only intended files. Commit any remaining session bookkeeping with an accurate message.

Then run, in order:

1. `git pull --rebase`
2. `bd dolt push`
3. `git push`
4. `git status`

Resolve and retry push failures when the remedy is in scope. Stop for credentials, conflicts requiring user judgment, or remote policy failures.

Report completed tasks, checks, commits, pushed branch, and remaining Beads issues. Do not say the session is complete unless Git reports the branch is current with its upstream.
