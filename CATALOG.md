# Skill catalog

| Skill | Description | Trigger | Mode |
| --- | --- | --- | --- |
| [unslop](skills/unslop/SKILL.md) | Remove AI writing patterns without losing meaning | All user-facing prose | Default |
| [technical-writing](skills/technical-writing/SKILL.md) | Precise engineer-facing docs, references and guides | Documentation, READMEs, RFCs, PR bodies | Automatic for docs |
| [grill-me](skills/grill-me/SKILL.md) | Uncover decisions with one question per round and recommendations | "grill me", "stress-test this idea" | Explicit |
| [sharpen](skills/sharpen/SKILL.md) | Make a task deeper, not larger; rewrite a better prompt | "sharpen this", "improve the brief" | Explicit |
| [architect](skills/architect/SKILL.md) | Ground, compare structural designs, sketch API before implementation | Nontrivial design, architecture, module boundaries | Task-triggered |
| [benchmark-checklist](skills/benchmark-checklist/SKILL.md) | Check whether speedup measurements are valid and relevant | Benchmark, speedup, performance comparison | Task-triggered |
| [blast-radius](skills/blast-radius/SKILL.md) | Prove hidden effects of changes outside their direct call sites | "what could this break", risky refactor | Task-triggered |
| [interrogate](skills/interrogate/SKILL.md) | Adversarial review with verified defects and severity | "interrogate", "adversarial review" | Explicit |
| [why](skills/why/SKILL.md) | Reconstruct historical rationale using commits, issues and code | "why is it built this way" | Task-triggered |
| [correct](skills/correct/SKILL.md) | Make recurring mistakes harder or impossible through architecture and checks | "correct", repeated agent errors | Explicit |

All skill files use the portable `name` / `description` frontmatter pattern. No guarantee of native auto-discovery exists for every harness. See [docs/harnesses.md](docs/harnesses.md).
