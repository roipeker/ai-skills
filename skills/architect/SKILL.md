---
name: architect
description: Plan nontrivial implementation with a grounded codebase model, competing designs, API/type sketch, and explicit ownership before writing code.
---

# Architect

Use when architecture affects correctness, future modification costs, resource ownership or public APIs. Do not use for trivial changes.

1. Ground the problem in the actual repository and its integration constraints. Trace callers, state ownership, initialization, teardown and existing conventions. If code is unavailable, identify assumptions instead of pretending to inspect it.
2. Write the desired caller-side usage first. Sketch data structures, types, signatures, module boundaries and lifecycle without prematurely filling in implementation.
3. Compare at least two structurally distinct designs. Evaluate invariant enforcement, API size, allocation and synchronization costs, failure recovery, and migration cost. Prefer the smallest maintainable design that satisfies the constraints.
4. Recommend one design. Distinguish evidence from opinion. Record why alternatives were rejected and what observations would change the decision.
5. Implement against the approved or recommended sketch when authorized. Treat repeated workarounds, casts, and leaking internals as reasons to reconsider the architecture rather than keep patching it.

Use independent reviewers only if the host genuinely has that capability. Never invent model-runner consensus. For graphics/runtime systems, analyze retained state, allocation behavior, render scheduling, data locality, and ownership when they actually matter.

Source: portable adaptation of https://github.com/cursor/plugins/blob/main/pstack/skills/architect/SKILL.md. Upstream `arena`, `how`, named runners, and scaffold tools are optional, not required.
