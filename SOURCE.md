Vendored from https://github.com/mattpocock/skills
Upstream: skills/productivity/writing-for-agents
File: SKILL.md -> skills/writing-for-agents/SKILL.md
File: SKILL-MECHANICS.md -> skills/writing-for-agents/SKILL-MECHANICS.md
Commit: 321658273cb1d20b76026717d027d505790106d4 (2026-08-19)
Merge: three-way
Pulled: 2026-09-19
License: MIT (upstream LICENSE, Matt Pocock)
Dropped: agents/openai.yaml (Codex-only metadata)

The lines above are read by scripts/upstream. `Upstream:` is the
directory the pin tracks, one `File:` per vendored file as
UPSTREAM_NAME -> LOCAL_PATH, `Commit:` the newest upstream commit to
that directory when the files were last pulled, and `Merge: three-way`
means a pull merges upstream changes since the pin under the local edits;
the description line in SKILL.md is local.

To update: `scripts/upstream check` lists upstream commits since the pin
and shows the diff; `scripts/upstream pull` merges upstream changes under the local
edits and moves the pin. Review the diff and commit.
