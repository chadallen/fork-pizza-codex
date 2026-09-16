---
name: build-tasks
description: Build ready Beads tasks with bounded Codex implementer and reviewer subagents, then verify, close, and push each approved frontier.
---

# Build Tasks

Implement one task, selected task IDs, or an epic. Use separate agent contexts for implementation and review.

Read [implementer.md](references/implementer.md) before dispatching implementers and [reviewer.md](references/reviewer.md) before dispatching reviewers.

## Select work

Run `bd prime` and read applicable `AGENTS.md` files. Resolve the requested scope with Beads JSON output. Stop for nonexistent tasks, unresolved blockers, or a dirty working tree.

Build a frontier of up to three ready tasks. Run tasks together only when their expected files do not overlap. Claim every task in the frontier before delegation.

Without an explicit auto-run request, show the scope and ask whether to run through completion or stop after each frontier.

## Implement

Spawn one implementer per frontier task using the runtime's subagent tools. Run independent assignments concurrently when available.

Each assignment must include the complete Beads task, applicable project instructions, sibling ownership boundaries, and the implementer reference. The main agent must not duplicate the implementer's codebase exploration.

Wait for every implementer. Confirm each task produced commits tagged with its task ID. Treat uncommitted changes, missing checks, or unresolved blockers as incomplete work.

## Review

Spawn a fresh reviewer for each implemented task. Reviewers receive the task, base commit, implementation commits, applicable instructions, and reviewer reference.

A reviewer returns `APPROVED` or `NEEDS_CHANGES` with evidence. It must not edit the implementation.

For `NEEDS_CHANGES`, send the findings to a fresh implementer assignment. Repeat review after fixes. Stop and report when progress needs user judgment.

## Integrate

After all reviews pass:

1. Inspect the combined frontier diff.
2. Run repository-level validation affected by the combined changes.
3. Resolve integration failures through another bounded implementation and review cycle.
4. Close approved tasks with specific reasons.
5. Push Beads state, then push Git commits.
6. Recompute the next frontier.

In checkpoint mode, stop after the frontier summary. In auto mode, continue until the selected scope is complete or blocked.

Never close a task based only on an implementer's self-report. Never let one subagent expand the selected scope or perform the final push.
