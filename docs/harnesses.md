# Harness integration

## Portable contract

Each skill lives at `skills/<slug>/SKILL.md` with YAML `name` and `description`. `AGENTS.md` contains the routing rules. A compatible agent should read the catalog, match the request, open the selected skill, then execute only supported steps.

## ChatGPT

ChatGPT cannot install a public GitHub directory as a native skill merely by being given its URL. If GitHub access is available, the user can say: "Use the skills from roipeker/ai-skills; read AGENTS.md and the matching SKILL.md." For future chats, a preference may help with routing but does not load GitHub files. Re-fetch the canonical file when exact current rules matter.

## Codex / OpenCode

Keep `AGENTS.md` in the workspace root or link/copy its instructions into the project's existing AGENTS.md. Place the `skills` directory where the specific runner's skill discovery expects it, or instruct the runner to read the relative paths directly. Avoid symlink assumptions on remote systems or sandboxed runners.

## Claude Code

Read `CLAUDE.md`; register the skill directories with the current Claude Code skill discovery mechanism if supported. The files do not require Claude models; a Claude-specific Skill tool invocation is an implementation detail, not the content of the skill.

## Cursor

Keep `.cursor/rules/ai-skills.mdc` alongside accessible `skills/`. Use the native Cursor skill registry if desired, but do not assume pstack plugin dependencies or configured model-runner aliases.

## Limitations

- Conversation-only hosts can reason over code, but cannot claim runtime verification without execution tools.
- External tools and model orchestration are optional, not silently simulated.
- Never install project-specific rules globally without consent.
- Upstream changes are not live-synced. Review `SOURCES.md` and compare content before upgrading.
