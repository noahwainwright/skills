# Skills

Skills for coding agents that help a product team decide a feature before it's built. Each skill is one `SKILL.md` in its own folder under `skills/`.

| Skill | What it does |
|---|---|
| [edge-cases](skills/edge-cases) | Finds what nobody has decided about a feature yet, asks one question at a time with a recommended answer, and saves `edge-cases.md` next to the spec. |

## Install

Claude Code, one skill:

```bash
mkdir -p ~/.claude/skills/edge-cases && curl -fsSL https://raw.githubusercontent.com/noahwainwright/skills/main/skills/edge-cases/SKILL.md -o ~/.claude/skills/edge-cases/SKILL.md
```

Any other coding agent: paste the skill's `SKILL.md` into the chat, then point it at the feature.

## License

MIT. See [LICENSE](LICENSE).
