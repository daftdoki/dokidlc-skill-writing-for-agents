# dokidlc-skill-writing-for-agents

A Claude Code plugin that carries one skill, `writing-for-agents`: the
reference for writing any document an agent reads. Skills, `AGENTS.md`,
`CLAUDE.md`, a doc reached by a pointer. It covers context pointers, the
two loads, the information hierarchy, completion criteria, leading words,
and pruning.

The text is Matt Pocock's, from
[mattpocock/skills](https://github.com/mattpocock/skills), vendored at
the commit named in `SOURCE.md`. MIT, his copyright, in `LICENSE`. One
local edit: the `description` line in `SKILL.md`, rewritten on
2026-09-20 so the skill fires on every kind of model-facing text, not
only skills and CLAUDE.md. Upstream pulls merge under it.

## Install

From the dokidlc marketplace:

```
claude plugin install writing-for-agents@dokidlc
```

The skill loads as `writing-for-agents:writing-for-agents`. It is
model-invoked: the agent reaches for it when it creates or edits a skill
or an agent-facing document.

## Update from upstream

```
scripts/upstream check     upstream commits since the pin, and the diff
scripts/upstream pull      merge upstream changes under the local edits, move the pin
```

Both need `gh` logged in. After `pull`, review the diff and commit.

## Layout

```
.claude-plugin/plugin.json          manifest
skills/writing-for-agents/          SKILL.md and SKILL-MECHANICS.md
SOURCE.md                           upstream, files, pin; read by scripts/upstream
scripts/upstream                    check and pull
LICENSE                             MIT, Matt Pocock
```
