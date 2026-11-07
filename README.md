# good-writing

An Agent Skill for developing ideas through writing, based on Paul Graham's [Good Writing](https://www.paulgraham.com/goodwriting.html).

## Approach

- Revise thought and expression together through small changes and fresh reading.
- Let sentence structure follow the idea, preserving the author's language and voice.
- Keep facts and qualifications intact; readable prose does not establish truth.

## Install

Ask Codex:

```text
Use $skill-installer to install https://github.com/ZepinLi/good-writing/tree/main/good-writing into ~/.agents/skills/good-writing.
```

The inner `good-writing/` directory is the standalone skill. Installation copies a version; later repository changes require updating the installed copy.

## Use

```text
Use $good-writing to revise this essay, improving the reasoning and prose together. Preserve my voice and briefly explain consequential changes.
```

```text
Use $good-writing to develop these notes into a short essay without inventing facts.
```

The skill also activates for matching requests and respects proofreading-only instructions.

## References

- [Source argument map](good-writing/references/paul-graham-argument-map.md): Graham's claims and the skill's operating boundaries.
- [Revision examples](good-writing/references/revision-examples.md): invented demonstrations of compression, expansion, qualification, and organization.

The workflow and examples adapt Graham's ideas; they are not his prescribed procedure or original prose.
