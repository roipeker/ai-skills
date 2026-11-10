---
name: correct
description: Stop recurring agent coding mistakes by finding repeated failure classes and preventing them with architecture, types, lint checks or tests.
---

# Correct

Inspect recurring failures in review comments, history, regressions and user corrections. Only call a pattern recurring when supported by repeated examples. Find the highest enforceable level that prevents it: simplify architecture and ownership first; encode invariants in types next; use lints and CI checks after that; use regression tests for behavior; put purely judgment-based rules in documentation last.

Prove a proposed enforcement fails on a representative previous mistake. Check that the rule does not ban valid implementations or increase maintenance cost without benefit. Keep a concise table connecting each recurring error to its enforcement and test. Do not invent previous failures or claim tests were run without tools.

Source: portable adaptation of https://github.com/cursor/plugins/blob/main/pstack/skills/correct/SKILL.md.
