# dokidlc-skill-writing-for-agents

A Claude Code plugin that carries one skill: how to write a document a model will read and act on.

The skill covers any text whose reader is an agent rather than a person. A `SKILL.md` and its description line, `CLAUDE.md` or `AGENTS.md`, a subagent or slash-command file, the text a hook prints into context, a docs page a pointer names, a system prompt. It gives the agent seven things to work with: context pointers, the two loads, the information hierarchy, steps and completion criteria, when to split, leading words, and pruning. `SKILL-MECHANICS.md` sits behind a pointer and holds frontmatter, invocation, and router skills, loaded only when the document being written is itself a skill.

The text is Matt Pocock's, from [mattpocock/skills](https://github.com/mattpocock/skills), vendored at the commit `SOURCE.md` pins. One line is local: the skill's `description`, rewritten so it fires on every kind of model-facing text rather than skills and `CLAUDE.md` alone. Upstream pulls merge under that edit.

## Why vendored rather than upstream

Installing from upstream means the skill can change under a project between sessions, and this skill decides how every other skill in the kit gets written. Pinning a commit makes that change a reviewed step instead of a surprise. The local description line is the second reason: upstream's fires on skills and `CLAUDE.md`, and the agents here write hook text, subagent files, and reference pages that need the same rules.

It is not a style guide for prose a person reads. That is [unslop](https://github.com/daftdoki/dokidlc-skill-unslop), which installs beside it.

Status: maintained by hand, at upstream `3216582` (2026-08-19), last pulled 2026-09-19.

## Install

From the dokidlc marketplace:

```
claude plugin install writing-for-agents@dokidlc
```

Nothing else is needed. The skill is model-invoked: the agent reaches for it when it writes or edits a skill, an `AGENTS.md`, or another document an agent reads.

## Run it

Ask the agent for a skill, a `CLAUDE.md`, or a subagent file, and it loads the skill first. To see what it then has in context:

```
grep '^##' skills/writing-for-agents/SKILL.md
```

```
## Context pointers
## The two loads
## Information hierarchy
## Steps and completion criteria
## When to split
## Leading words
## Pruning
```

## Caveats

- The skill fires on its description, so it can miss a document whose purpose is not obvious from the request. Name the skill when you want it for sure.
- A pull can conflict with the local description line. `scripts/upstream pull` merges upstream under it and leaves the conflict for you.
- Both `scripts/upstream` verbs need `gh` logged in.

## Other docs

- [skills/writing-for-agents/SKILL.md](skills/writing-for-agents/SKILL.md) is the skill, and `SKILL-MECHANICS.md` beside it is the reference it points at.
- [SOURCE.md](SOURCE.md) is the upstream pin and the vendoring rules, and it is what `scripts/upstream check` and `pull` read to update the copy.

Questions and bugs go to the [issue tracker](https://github.com/daftdoki/dokidlc-skill-writing-for-agents/issues). Anything about the skill's content belongs upstream.

## License

MIT, Matt Pocock. See [LICENSE](LICENSE).
