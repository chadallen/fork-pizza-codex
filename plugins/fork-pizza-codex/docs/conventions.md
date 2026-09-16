# Workflow Conventions

## Beads

- Use `bd` for all task tracking when `.beads/` exists.
- Use `--json` when command output must be parsed.
- Include the task ID in implementation commits: `git commit -m "<message> (<task-id>)"`.
- Close tasks only after an independent review and integration checks pass.
- Use one closed `session-log` issue per completed session.

## Project instructions

Read `AGENTS.md` files from the repository root through the directories being changed. Apply `AGENTS.override.md` where present.

Keep project instructions focused on facts needed in every task: commands, constraints, and repository conventions. Put session history in Beads issues and procedures in skills.

## Agent boundaries

The main agent owns task selection, Beads state, integration, closing tasks, and pushing. Implementers change and commit code. Reviewers inspect the implementation independently and do not repair it.

Do not hardcode model names. Use the runtime's configured model and available delegation tools.
