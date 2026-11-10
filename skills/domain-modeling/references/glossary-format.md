# Glossary format

Use a `GLOSSARY.md` per bounded context or a single root glossary. An optional `GLOSSARY-MAP.md` describes multiple contexts.

```md
# Cloud files

The concepts used by the local file and remote storage integration.

## Language

**Remote file**:
A file represented by the cloud storage provider.
_Avoid_: Cloud object, server file

**Local cache**:
A locally stored copy of content obtained from a remote file.
_Avoid_: Local mirror
```

Definitions should describe what a concept **is** in one or two sentences. List terms to avoid only when they are genuinely ambiguous. Use project-specific domain concepts, not general programming concepts. Group terms only when the domain warrants it. A glossary is not an implementation specification.

Derived from https://github.com/mattpocock/skills/blob/main/skills/engineering/domain-modeling/GLOSSARY-FORMAT.md.
