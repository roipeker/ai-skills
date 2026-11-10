# ADR format

Create `docs/adr/` only when needed. Use sequential file names such as `0001-cache-ownership.md`.

```md
# Cache ownership

We chose one cache owner per remote account because concurrent writers could invalidate an open file. A shared global cache was rejected because it coupled account lifecycles.
```

Only record an ADR when all three are true: hard to reverse, surprising without context, and the result of a meaningful trade-off.

Add status, options or consequences sections only when they clarify the decision. Use existing project conventions when available.

Derived from https://github.com/mattpocock/skills/blob/main/skills/engineering/domain-modeling/ADR-FORMAT.md.
