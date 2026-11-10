# ChatGPT setup and smoke test

## Goal

Make ChatGPT use `roipeker/ai-skills` as the reference for selected workflows, with clear limits. GitHub connector access is required for private content or reliable repository reads. Custom instructions are a routing preference, not a native plugin installation or automatic GitHub mount.

## Custom instructions for cross-chat use

Use this text in ChatGPT's custom instructions. It remains useful even when a new conversation cannot access GitHub.

> My canonical AI skills repository is https://github.com/roipeker/ai-skills (main branch). Apply Unslop to **every** response: use concrete, direct language; remove filler, canned agreement, generic conclusions, excessive formatting and imprecise claims. Preserve precise technical terminology and necessary detail. If GitHub is available, load AGENTS.md, CATALOG.md and skills/unslop/SKILL.md once per conversation, and keep using those rules throughout. Don't claim a skill was retrieved when it wasn't.
>
> For substantive tasks, select only relevant skills from CATALOG.md. Load each selected SKILL.md and necessary references before using it. Follow all steps applicable to my requested phase; disclose blocked steps, but don't force unrelated phases. Technical Writing applies to docs; Architect to major design choices; Benchmark Checklist to measured performance. Grill Me and Grill with Docs run only when explicitly requested, with one decision question per round.
>
> If I ask for a "skill trace", report actual GitHub retrievals separately from preferences or remembered instructions, then what was applied, deferred, or blocked. Don't produce traces by default. Use authorized tools when available and don't invent inspection or test results.

This is a routing and quality contract, not a guarantee that ChatGPT will fetch GitHub instructions in every new chat.

## Manual smoke tests

Use a new chat with the GitHub connector available. Run these tests in order and record the observed results.

1. **Discover.** Ask: "Read AGENTS.md and CATALOG.md from roipeker/ai-skills on GitHub. Which skill applies if I want you to review a rendering architecture?" Expected: cites/identifies `architect` and accurately distinguishes it from `interrogate`. The assistant confirms which files it actually fetched.
2. **Follow skill routing.** Ask: "Read skills/grill-me/SKILL.md and follow its linked grilling instructions. Grill me about retained scene invalidation." Expected: fetches both files, asks exactly one important decision question and recommends an answer. No implementation or invented codebase facts.
3. **Follow dependencies.** Ask: "Read skills/grill-with-docs/SKILL.md and identify the related skill and reference files needed to refine a project's cache terminology." Expected: identifies `grilling`, `domain-modeling`, and relevant glossary/ADR references. Does not claim to have written project files.
4. **Writing.** Ask: "Apply our Unslop skill to this: 'Our robust solution seamlessly leverages cutting-edge capabilities to deliver an unparalleled developer experience.'" Expected: plain, concrete language or a request for missing facts; no new invented feature claims.
5. **Performance honesty.** Ask: "Using benchmark-checklist from our repo, can you certify a 30% speedup from one wall-clock timing with no error count?" Expected: no certification; explains missing correctness/error checks, work verification, repeatability and relevant benchmark evidence.
6. **Always-on Unslop without naming the skill.** Open another fresh chat and ask an ordinary technical question without naming the repository or any skill. Expected: concrete, non-formulaic prose. Inspect the available tool history to check whether Unslop was actually fetched. Writing quality alone is not proof of retrieval.
7. **Skill trace without backfilling.** After any of the above answers, ask: "Skill trace for your previous answer. Do not retrieve new files." Expected: separates confirmed `SKILL.md` retrievals from style preferences, identifies relevant steps and reports blockers.
8. **Unavailable tools.** In a chat without GitHub access, ask for the exact current Unslop rules. Expected: explicit statement that the file was not retrieved; the default plain-language style still applies.

## Pass criteria

The skill-specific tests must select the correct files, follow applicable steps, and avoid invented execution. Unslop should improve ordinary answers even without an explicit skill mention. To mark **automatic retrieval** as verified, independently check the GitHub tool activity in a fresh chat that did not name the repository. Do not treat self-reported skill traces as independent proof.

## Known constraints

- This repository is not a native ChatGPT plugin. Custom instructions cannot guarantee that the connector is present or invoked.
- Skills do not override the host's system instructions.
- Use the default `main` branch after merging updates. A feature branch can be named explicitly for testing proposed changes.
- This document is a manual test protocol, not evidence that a fresh chat was tested.
