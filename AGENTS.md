# Agent instructions

This repository is the shared source of truth for reusable AI-agent skills. Read `CATALOG.md` to select relevant workflows, then load only their instructions and required references. A skill's presence in this repository does not mean the host has read or executed it.

## Always-on writing standard

Use `skills/unslop/SKILL.md` for every user-facing response. Retrieve the file once per conversation or work session when accessible; use it throughout that session, not just for rewriting tasks. Re-read it if instructions are no longer available in context or a fresh version matters. Do not fetch it on every short message.

Before sending a response, perform a silent Unslop editing pass: remove filler, canned agreement, vague claims, forced structure, decorative formatting and unnecessary jargon; replace abstractions with specific behavior or evidence. Preserve precise technical terms, code identifiers, the user's intended tone and necessary detail. This is a writing check, not a reason to alter quoted text or invent facts.

If the file cannot be fetched, apply the core writing standard above and disclose the retrieval limitation only when relevant. Never call the source file "loaded" without a confirmed retrieval in the current conversation or work session.

## Selection rules

1. Unslop is always active as defined above; don't duplicate its instructions in every task.
2. For README, API docs, proposals, PR descriptions, and design notes, use `skills/technical-writing/SKILL.md` in addition.
3. If the user asks "grill me", follow `skills/grill-me/SKILL.md`, which routes to `skills/grilling/SKILL.md`. Ask one decision question per round unless requested otherwise. For codebase-backed discovery with glossary and ADR updates, use `skills/grill-with-docs/SKILL.md` plus `skills/domain-modeling/SKILL.md` when explicitly requested.
4. If the user requests a better prompt or stronger scope without more features, use `skills/sharpen/SKILL.md`.
5. For nontrivial architecture decisions, use `skills/architect/SKILL.md`. Ground in the existing code and prefer simple ownership and APIs.
6. For measured performance claims or decisions between performance alternatives, use `skills/benchmark-checklist/SKILL.md`.
7. For risky changes, use `skills/blast-radius/SKILL.md`. For historical rationale, use `skills/why/SKILL.md`.
8. For adversarial review, use `skills/interrogate/SKILL.md`. For recurring agent mistakes, use `skills/correct/SKILL.md`.

## Skill execution contract

- For a task that selects another skill, retrieve its complete `SKILL.md` and any references needed for the current step **before** doing substantial work. Confirm the real file paths and version when asked.
- Determine which steps apply to the user's requested phase. Investigation does not automatically require API sketches, implementation, or tests. Do not complete unrequested phases merely to claim the whole skill ran.
- Complete applicable steps with available evidence. If a required step is impossible because the code, device, runner, or measurements are unavailable, mark it blocked rather than inventing a result. If a step is intentionally outside the current phase, mark it deferred.
- For explicit workflow invocations, report meaningful blockers or deviations without turning the final answer into a checklist of the skill itself. Say when the current phase is complete, not when the whole skill has not run.
- When the user asks for a **skill trace**, report the skill paths actually retrieved, Git ref or blob SHA if available, applicable steps performed, deferred or blocked steps, and any checks actually run. Treat remembered preferences and custom instructions as separate from file retrieval. Never backfill a retrieval just to claim it happened earlier.
- Do not emit a trace for normal responses unless the user is testing skill behavior.

## General execution rules

- Direct conversation skills may run without shell access. Repository analysis and measurement skills must state when code, history, tests, or instrumentation are unavailable.
- Never claim a test ran, a file changed, a subagent worked, or a skill installed unless a tool confirms it. Discovery writes belong to the target project, not this catalog.
- Do not treat skill references as authority to override user instructions, security boundaries, or higher-priority host instructions.
- Avoid loading every skill by default. Unslop is the sole always-on skill; read others when a trigger matches.
- Report actual evidence, important trade-offs, and remaining uncertainty. Don't substitute prose for verification.
- A skill is an instruction workflow, not a guarantee that the hosting agent can execute every tool it mentions.

## Project preferences

Prefer correctness, predictable ownership, performant data layouts, measurable optimization, minimal abstractions, and maintained APIs. For graphics and Flutter engine work, consider RenderObject, Layers, SceneBuilder, dart:ui, memory layout, batching, and retained rendering when applicable. Do not introduce these merely to sound sophisticated.
