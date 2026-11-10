---
name: grilling
description: Interview the user about a plan or design, track prerequisite decisions and recommend answers; use for "grill me", "grilling", or explicit discovery.
---

# Grilling

Map the work as a decision tree. The frontier contains questions whose prerequisites are settled. Distinguish facts the agent can verify from choices that belong to the user. Investigate available facts using current tools before asking; never invent evidence.

Ask **one decision question per round** by default. State a concrete recommendation and its rationale. Explain significant trade-offs, make "yes" accept your recommendation, and wait for the user's answer. If the user explicitly requests multiple questions, ask only mutually independent frontier questions.

Carry forward settled decisions and constraints, including budgets, deadlines, validation gates and definitions. After each answer, recompute the frontier. Do not revisit settled decisions without new evidence or an explicit user change. Where evidence is missing, recommend a validation method rather than guessing.

Continue until important branches are resolved. Summarize the decision record, remaining uncertainties, and next steps. If this is discovery before implementation, obtain approval before executing the design. If the user has asked for a working artifact rather than an interview, do not invoke this skill on their behalf.

## Execution portability

Use available web, code, GitHub, file, or remote-machine access for research. Parallel subagents are optional; never claim they ran unless the harness actually launched them. No special Skill tool is required.

Adapted from https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md (MIT, Matt Pocock). This version asks one question at a time by default.
