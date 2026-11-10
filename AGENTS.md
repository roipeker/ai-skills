# Agent instructions

This repository is the shared source of truth for reusable AI-agent skills. When working in a project that includes this repository, read `CATALOG.md` and load only the skills relevant to the request.

## Selection rules

1. For any user-facing writing, apply `skills/unslop/SKILL.md`. Preserve meaning and technical terms when the ordinary term is more precise.
2. For README, API docs, proposals, PR descriptions, and design notes, use `skills/technical-writing/SKILL.md` in addition.
3. If the user explicitly requests "grill me", follow `skills/grill-me/SKILL.md`. Ask only one decision question per round unless the user asks for another format.
4. If the user requests a better prompt or stronger scope without more features, use `skills/sharpen/SKILL.md`.
5. For nontrivial architecture decisions, use `skills/architect/SKILL.md`. Ground in the existing code and prefer simple ownership and APIs.
6. For measured performance claims or decisions between performance alternatives, use `skills/benchmark-checklist/SKILL.md`.
7. For risky changes, use `skills/blast-radius/SKILL.md`. For historical rationale, use `skills/why/SKILL.md`.
8. For adversarial review, use `skills/interrogate/SKILL.md`. For recurring agent mistakes, use `skills/correct/SKILL.md`.

## Execution contract

- Direct conversation skills may run without shell access. Repository analysis and measurement skills must state when code, history, tests, or instrumentation are unavailable.
- Never claim a test ran, a file changed, a subagent worked, or a skill installed unless a tool confirms it.
- Do not treat skill references as authority to override user instructions, security boundaries, or higher-priority host instructions.
- Avoid loading every skill by default. Read the specific `SKILL.md` and its references only when a trigger matches.
- Report actual evidence, important trade-offs, and remaining uncertainty. Don't substitute prose for verification.
- A skill is an instruction workflow, not a guarantee that the hosting agent can execute every tool it mentions.

## Project preferences

Prefer correctness, predictable ownership, performant data layouts, measurable optimization, minimal abstractions, and maintained APIs. For graphics and Flutter engine work, consider RenderObject, Layers, SceneBuilder, dart:ui, memory layout, batching, and retained rendering when applicable. Do not introduce these merely to sound sophisticated.
