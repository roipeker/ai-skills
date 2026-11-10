---
name: interrogate
description: Perform skeptical architecture or code review, attempting to disprove important safety, correctness and performance claims with reproducible counterexamples.
---

# Interrogate

Review the implementation or design as a skeptical maintainer. Identify the strongest claimed invariants, find their weakest assumptions, and search for concrete counterexamples. Prioritize correctness, resource lifetime, concurrency, failure recovery, API behavior, security, and measurable performance.

For each finding, record the affected symbol or file, trigger, observed or reasoned failure, severity, and verification evidence. Demonstrate the issue with tests or runtime behavior when tools are available. Distinguish a confirmed defect from a hypothesis and avoid speculative laundry lists.

Ask whether the fix creates another class of failure or unnecessary complexity. Recommend the smallest root-cause correction and a regression check. Report when the review found no verified defects, without claiming the code is proven correct.

Do not claim multiple independent agents reviewed the code unless they actually ran.

Source: portable adaptation of https://github.com/cursor/plugins/blob/main/pstack/skills/interrogate/SKILL.md.
