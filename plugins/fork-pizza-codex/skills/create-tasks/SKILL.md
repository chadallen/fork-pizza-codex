---
name: create-tasks
description: Turn an approved discussion or specification into Beads tasks and dependencies after presenting a reviewable proposal.
---

# Create Tasks

Create Beads tasks from a file argument or the current conversation. Do not create records until the user approves the proposal.

## Gather context

Initialize Beads if `.beads/` is absent. Read the supplied specification in full, or use the current discussion. Ask only for information required to define verifiable outcomes.

Inspect the code that proposed tasks will affect. Add prerequisite refactoring only when the existing structure makes the requested change unsafe or duplicative.

## Propose

Use one task for one clear change. Use an epic when the work has three or more tasks or needs grouped progress tracking.

For each task provide:

- imperative title
- concise description and likely files
- design constraints when not obvious
- observable acceptance criteria
- dependencies on other proposed tasks
- priority from P0 through P4

Show the complete proposal. Apply requested edits and show the revised proposal. Wait for an explicit confirmation.

## Create

After approval:

1. Create the epic when needed.
2. Create each task with its description, design, acceptance criteria, priority, and parent.
3. Add dependencies with the dependent task first.
4. Verify the resulting graph with `bd show`, `bd ready`, and `bd blocked` as JSON.
5. Commit Beads changes using the repository's instructions and run `bd dolt push` when configured.

Report created IDs, dependencies, and the next ready task. Do not start implementation.
