---
name: domain-modeling
description: Define precise domain vocabulary, challenge ambiguous terms and edge cases, and record significant architectural choices in project-local glossaries and ADRs.
---

# Domain modeling

Use when project-specific terminology or ownership is being defined or changed, not whenever a glossary is merely read.

- Read existing `GLOSSARY.md`, `GLOSSARY-MAP.md` and relevant ADRs before changing terms.
- Challenge overloaded terms with a concrete example. Distinguish user, customer, account, remote, cache and other concepts only when meaningful to the actual project.
- Use edge cases to expose mistaken boundaries or ambiguous lifecycles; compare claims with inspected code when available.
- When a term is resolved, add a compact definition and deprecated synonyms to the correct project's glossary. Keep implementation decisions out of glossary definitions. Use [glossary format](references/glossary-format.md).
- For multiple bounded contexts, respect a root `GLOSSARY-MAP.md` and put terms with their owning context. Otherwise a single root glossary is enough.
- Create an ADR only when a choice is hard to reverse, surprising without context, and based on genuine alternatives. Use [ADR format](references/adr-format.md).
- Create files lazily and write only with authorized repository access. If tools are missing, provide proposed changes instead of claiming a write.

Adapted from https://github.com/mattpocock/skills/blob/main/skills/engineering/domain-modeling/SKILL.md (MIT, Matt Pocock).
