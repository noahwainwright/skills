# Edge cases

A skill for coding agents that finds what nobody has decided about a feature yet. Point it at a spec, tickets, the code, or a few lines describing the feature. It asks one question at a time, each with a recommended answer, and saves `edge-cases.md` next to the spec.

## How it works

1. **Read**: reads the spec and notes what's decided.
2. **Find**: confirms the core job, then walks five checks: Steps, Time, Roles, Data and Exits.
3. **Group**: groups the cases by cause and names the one to decide first.
4. **Ask**: asks one question at a time, with a recommended answer.
5. **Write**: saves `edge-cases.md` with one row per case.

A question you can't answer keeps its recommended answer as the default and is marked "Needs decision". Those rows stay in the file as open questions for the feature owner.

## Install

Claude Code:

```bash
mkdir -p ~/.claude/skills/edge-cases && curl -fsSL https://raw.githubusercontent.com/noahwainwright/skills/main/skills/edge-cases/SKILL.md -o ~/.claude/skills/edge-cases/SKILL.md
```

Any other coding agent: paste the contents of [`SKILL.md`](SKILL.md) into the chat, then point it at the feature.

## Use

```text
Run the edge-cases skill on docs/invoice-export.md
```

No spec? Describe the feature in a few lines instead.

## What you get

`edge-cases.md` next to the spec:

| Column | Contains |
|---|---|
| ID | H1 for the happy path, then E1, E2 and so on |
| Status | "Ready" or "Needs decision" |
| Scenario | The state that differs from the happy path |
| Trigger | The event, with its before, during or after timing |
| Expected | What the product does |
| Fallback | What the product does when the normal task can't finish |

Under the table: the constraint (the case to decide first), the cases its decision covers, and the open questions with their owner and default.

## License

MIT. See [LICENSE](../../LICENSE).
