# Foundation verification

Initial manual verification: 2026-11-10.

## Checks performed

- GitHub connector retrieved `AGENTS.md`, `CATALOG.md`, the 13 `skills/*/SKILL.md` files, two domain-modeling references, the two MIT license files, and the Cursor rule file from `feat/portable-skills-catalog`.
- The vendored `unslop`, `sharpen`, and `benchmark-checklist` files exactly match their current source contents in `cursor/plugins`. Their Git blob hashes match.
- `grill-me` links to `grilling`; `grill-with-docs` links to `grilling` and `domain-modeling`; `domain-modeling` links to its glossary and ADR format references. The target files were retrieved successfully.
- The initial pull request remains a review branch, not merged into `main`.

## Not yet verified

- A new ChatGPT conversation with custom instructions enabled automatically selects and retrieves the correct skill.
- Each harness's native skill discovery recognizes the repository without explicitly reading `AGENTS.md`.
- Desktop Commander writes to a separate project and its permission boundaries behave correctly.
- End-to-end runtime execution of codebase-dependent skills.

See [ChatGPT setup and smoke test](chatgpt-setup.md) to verify new-chat behavior. Do not mark these checks successful from document review alone.
