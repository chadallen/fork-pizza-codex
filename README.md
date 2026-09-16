# fork-pizza-codex

A Codex-native coding workflow built around [Beads](https://github.com/steveyegge/beads). It orients sessions, turns requirements into tracked tasks, delegates implementation and review, and closes sessions with verified commits and pushes.

## Requirements

- Codex
- Beads (`bd`)
- Git

On macOS, install Beads with `brew install beads`.

## Install from this checkout

```bash
codex plugin marketplace add /Users/chadallen/projects/fork-pizza-codex
codex plugin add fork-pizza-codex@personal
```

Start a new Codex task after installation so the new skills load.

## Skills

| Skill | Purpose |
|---|---|
| `$start-session` | Read repository and Beads state, then propose a session plan. |
| `$create-tasks` | Turn a discussion or specification into approved Beads tasks. |
| `$build-tasks` | Implement ready tasks with separate implementation and review agents. |
| `$end-session` | Record the session, run checks, commit, sync Beads, and push. |

Each skill requires explicit invocation. The plugin uses `AGENTS.md` for project instructions and does not read `CLAUDE.md` as part of its workflows.

## License

MIT. See [LICENSE](LICENSE).
