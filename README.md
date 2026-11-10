# AI skills

Curated, portable agent skills for engineering and product work. Canonical instructions live in `skills/<name>/SKILL.md`. Each skill has a concise YAML description so an agent can select it based on the task.

## Usage

Read [AGENTS.md](AGENTS.md) first. Select a skill from [CATALOG.md](CATALOG.md), then read its entire `SKILL.md` before using it. Follow linked references only when relevant. Do not assume slash commands, subagents, local execution, or tools exist just because the upstream skill mentions them.

| Automatic defaults | Explicit or task-triggered |
| --- | --- |
| `unslop` for final prose; `technical-writing` for documentation | `grill-me`, `sharpen`, `architect`, `benchmark-checklist`, `blast-radius`, `interrogate`, `why`, `correct` |

## Harness installation

- **Codex, OpenCode and compatible agents:** clone this repository and place or link `AGENTS.md` in the working project. Keep the `skills/` paths accessible. Configure the harness's native skills directory to point to, or copy from, `skills/` if it supports skill discovery.
- **Claude Code:** add `CLAUDE.md` in the workspace or load these skill directories through Claude's skill discovery. There is no Claude subscription requirement to read these files.
- **Cursor:** use `.cursor/rules/ai-skills.mdc` and expose `skills/` through your workspace or Cursor's supported skill directory.
- **ChatGPT:** provide this GitHub repository in the conversation and request the relevant skill. With GitHub access, ChatGPT can fetch the files. GitHub files are **not automatically injected into every new ChatGPT conversation**. A memory preference is not a full replacement for loading the actual skill.

See [docs/harnesses.md](docs/harnesses.md) for specific guidance and limitations.

## Maintenance

Read [SOURCES.md](SOURCES.md) before updating a vendored or adapted skill. `unslop`, `sharpen`, and `benchmark-checklist` are upstream copies. Other skills are portable adaptations and must be reviewed when the upstream changes. No automatic upstream syncing or pin enforcement is implied.

Licensed upstream material retains its license under [licenses/pstack-MIT.txt](licenses/pstack-MIT.txt). Contributions and original adaptations must respect upstream attribution.
