# Sources and update policy

The initial curation was made on 2026-11-10.

| Local skill | Source | Policy |
| --- | --- | --- |
| unslop | https://github.com/cursor/plugins/blob/main/pstack/skills/unslop/SKILL.md | Vendored upstream text, local attribution |
| sharpen | https://github.com/cursor/plugins/blob/main/pstack/skills/sharpen/SKILL.md | Vendored upstream text, local attribution |
| benchmark-checklist | https://github.com/cursor/plugins/blob/main/pstack/skills/benchmark-checklist/SKILL.md | Vendored upstream text, local attribution |
| technical-writing | https://github.com/cursor/plugins/blob/main/pstack/skills/technical-writing/SKILL.md | Portable adaptation |
| architect | https://github.com/cursor/plugins/blob/main/pstack/skills/architect/SKILL.md | Portable adaptation; removes hardwired arena/model runners |
| blast-radius | https://github.com/cursor/plugins/blob/main/pstack/skills/blast-radius/SKILL.md | Portable adaptation |
| interrogate | https://github.com/cursor/plugins/blob/main/pstack/skills/interrogate/SKILL.md | Portable adaptation; no simulated subagents |
| why | https://github.com/cursor/plugins/blob/main/pstack/skills/why/SKILL.md | Portable adaptation |
| correct | https://github.com/cursor/plugins/blob/main/pstack/skills/correct/SKILL.md | Portable adaptation |
| grill-me | https://github.com/mattpocock/skills/blob/main/skills/productivity/grilling/SKILL.md | Portable adaptation; one question per round by user preference |

pstack is MIT licensed by Lauren Tan. See `licenses/pstack-MIT.txt`. The original `grill-me` wrapper in mattpocock/skills dispatches to `grilling`; the adapted skill here captures the procedure without requiring a native Skill tool.

## Update procedure

1. Retrieve each upstream source and note the current commit SHA. Compare the latest upstream instructions with the local skill.
2. For verbatim copies, replace the file only after reviewing changed behavior. Keep the original copyright/license notice.
3. For adapted skills, manually reconcile new upstream ideas with the portable constraints and local preferences.
4. Check routing descriptions, relative links, and harness behavior. Open a PR summarizing changes.
5. Do not overwrite local adaptations with upstream files or claim that a live-sync mechanism exists.

No upstream version pin or automated update workflow is configured in the initial release.
