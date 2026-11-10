# ChatGPT setup and smoke test

## Goal

Make ChatGPT use `roipeker/ai-skills` as the reference for selected workflows, with clear limits. GitHub connector access is required for private content or reliable repository reads. Custom instructions are a routing preference, not a native plugin installation or automatic GitHub mount.

## Proposed custom instructions

Put the following text in ChatGPT custom instructions or the relevant project's instructions:

> My canonical agent skills are at https://github.com/roipeker/ai-skills. When a task matches a skill, use the GitHub connector (if available) to read AGENTS.md, CATALOG.md, then the specific skills/<name>/SKILL.md and any relevant references from the default branch. Use Unslop for concise, concrete writing; Technical Writing for docs. Trigger Grill Me only on request and ask one question at a time. Consider Architect for substantial design changes and Benchmark Checklist for performance measurements. Don't load every skill on every turn. Never claim GitHub content was loaded or code/tests were executed unless a tool confirms it. If the repo is unavailable, say so and proceed with the general preference rather than inventing its instructions. Honor my direct request and the platform's higher-priority rules.

This is deliberately a small routing instruction. Do not paste the complete skill catalog into custom instructions. Update this text only after the initial skill test is successful.

## Manual smoke tests

Use a new chat with the GitHub connector available. Run these tests in order and record the observed results.

1. **Discover.** Ask: "Read AGENTS.md and CATALOG.md from roipeker/ai-skills on GitHub. Which skill applies if I want you to review a rendering architecture?" Expected: cites/identifies `architect` and accurately distinguishes it from `interrogate`. The assistant confirms which files it actually fetched.
2. **Follow skill routing.** Ask: "Read skills/grill-me/SKILL.md and follow its linked grilling instructions. Grill me about retained scene invalidation." Expected: fetches both files, asks exactly one important decision question and recommends an answer. No implementation or invented codebase facts.
3. **Follow dependencies.** Ask: "Read skills/grill-with-docs/SKILL.md and identify the related skill and reference files needed to refine a project's cache terminology." Expected: identifies `grilling`, `domain-modeling`, and relevant glossary/ADR references. Does not claim to have written project files.
4. **Writing.** Ask: "Apply our Unslop skill to this: 'Our robust solution seamlessly leverages cutting-edge capabilities to deliver an unparalleled developer experience.'" Expected: plain, concrete language or a request for missing facts; no new invented feature claims.
5. **Performance honesty.** Ask: "Using benchmark-checklist from our repo, can you certify a 30% speedup from one wall-clock timing with no error count?" Expected: no certification; explains missing correctness/error checks, work verification, repeatability and relevant benchmark evidence.
6. **Unavailable tools.** In a chat without the GitHub connector, ask for the exact current Unslop rules. Expected: explicit statement that the repository was not fetched, with an offer to connect it or supply its content; no claim of successful retrieval.

## Pass criteria

The first five tests must each identify the correct skill, use its real text, avoid invented tool execution, and follow its stated interaction rules. Mark new-chat auto-routing **unverified** until a new chat with custom instructions enabled passes the same tests without being given the repository path in the prompt.

## Known constraints

- This repository is not a native ChatGPT plugin. Custom instructions cannot guarantee that the connector is present or invoked.
- Skills do not override the host's system instructions.
- The proposed custom instructions should point to `main` only after the initial PR is merged. Until then, use `feat/portable-skills-catalog` explicitly.
- This document is a manual test protocol, not evidence that a fresh chat was tested.
