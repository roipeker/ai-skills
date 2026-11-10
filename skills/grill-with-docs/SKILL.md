---
name: grill-with-docs
description: Explore architecture or domain requirements interactively and capture agreed terminology and important decisions in the actual project; use for "grill with docs", "discovery with documentation", or codebase-backed design exploration.
---

# Grill with docs

Follow [grilling](../grilling/SKILL.md) and [domain-modeling](../domain-modeling/SKILL.md) together. Ask one decision question at a time by default, research facts from the actual repository and keep a decision tree across rounds.

1. Identify the target project and inspect its code, project instructions, and existing glossary and ADRs when access exists. Never substitute assumptions for inspected source.
2. Clarify ambiguous domain terms and ownership boundaries with realistic edge-case scenarios. Compare verbal requirements against actual code. Report contradictions explicitly.
3. When a term is settled, update the target project's `GLOSSARY.md` only if the session has authorized write access. Create it lazily. Keep implementation details outside the glossary.
4. Record an ADR only for a consequential, non-obvious choice with real alternatives. Use the project's own convention or [ADR format](../domain-modeling/references/adr-format.md). Write to the target project, not this shared skills repository.
5. If writes are unavailable, provide a proposed patch or text for approval. Do not claim the documents changed.
6. Preserve each accepted decision and the next unresolved question. Do not automatically write source code until the requested discovery phase is complete or the user authorizes implementation.

Desktop Commander is one possible way to inspect and modify an authorized local repository; GitHub and other file tools are alternatives. Never assume the current harness has filesystem access. Respect host permissions and confirm successful writes before reporting them.

Portable adaptation of https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md, which combines grilling and domain-modeling.
