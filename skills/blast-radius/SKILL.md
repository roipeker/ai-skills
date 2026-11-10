---
name: blast-radius
description: Identify hidden effects of a change beyond direct callers, and prove key safety assumptions with real code or tests when tools allow.
---

# Blast radius

Read the diff, call sites and affected invariants. Look for failures that a simple symbol search misses: cache invalidation, file formats, external APIs, ordering, retries, lifecycle, concurrency, async cancellation, retained resources and configuration interactions.

Find the one or two facts the change's safety depends on. Trace them to code, pinned dependencies or history. Reproduce a plausible bad case with the smallest executable test when available; preferably use the actual library or runtime. Report evidence level: inferred, source-backed, reproduced in a test, or reproduced in the app. Do not present an unexecuted test as proof.

Prioritize confirmed breakage and unresolved high-impact assumptions. Keep speculative possibilities separate. If execution is unavailable, provide the precise test that would settle the question.

Source: portable adaptation of https://github.com/cursor/plugins/blob/main/pstack/skills/blast-radius/SKILL.md.
