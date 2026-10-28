---
name: edge-cases
description: Find the edge cases in a feature before it is built. Reads the spec, walks five checks, asks one question at a time with a recommended answer, and saves edge-cases.md with a default for every open decision. Use when someone asks for edge cases, failure states, or "what can go wrong" on a feature, spec, PRD, tickets or code.
---

# Edge cases

Write `edge-cases.md` next to the spec before the build. Stop when each case has an answer or a default marked "Needs decision".

## How it works

1. **Read**: read the spec and note what's decided.
2. **Find**: confirm the core, then walk five checks.
3. **Group**: group the cases by cause and name the constraint.
4. **Ask**: ask one question at a time, with a recommended answer.
5. **Write**: save `edge-cases.md` and print the summary.

Find two decisions first: what happens with incomplete data, and what happens with an unknown state.

## Read the spec

- Read the spec, PRD, tickets or code the user points to. If there are none, use their description.
- Note stated policies and use them without asking for approval again.

## Find the cases

Confirm the core in one line each:

- **Core job**: the one thing the feature must do.
- **Happy path**: the steps when everything works.
- **User**: who uses it, and what they need from it.

Walk five checks. For each, list what can be missing, late, wrong or unknown:

- **Steps**: a step is skipped, repeated or abandoned.
- **Time**: it runs before, during or after the moment it expects, or times out.
- **Roles**: the user lacks a role, permission or context.
- **Data**: the data is missing, partial, wrong or out of date.
- **Exits**: the user cancels, goes back, or leaves and returns.

## Group the cases

Group cases that share a cause. Most fall under incomplete data or an unknown state.

Name the row whose decision settles the most other cases. In The 80/20, name each covered ID and all actions and timing settled without another choice. Shared causes, prior steps and self-coverage do not count. If none settles another, name the first row to decide and why, then write "No other cases are covered". Do not invent links.

## Ask only what's missing

Ask one question about one case and one choice. In the same turn, state a recommended action and why it helps, then wait for the answer.

Base each recommendation on one move: show the user what's missing or assumed, then give them a way back. If the user doesn't know, write the recommendation as the default and mark the case "Needs decision".

## Write edge-cases.md

Save `edge-cases.md` next to the spec, with one row per case:

| Column | Contains |
|---|---|
| ID | H1 for the happy path, then E1, E2 and so on |
| Status | "Ready" or "Needs decision" |
| Scenario | The state that differs from the happy path |
| Trigger | The event, keeping its before, during or after timing |
| Expected | What the product does |
| Fallback | A concrete product action when the normal task cannot finish |

For a Needs decision row, write proposed product actions in Expected and Fallback. Keep the decision label only in Status. Mark Ready only for a policy stated in the spec or a user reply. Leave other rows Needs decision.

Example only: `E1 | Needs decision | The title is missing. | The user clicks Save. | Ask for a title. | Keep the draft.`

Use one sentence per cell with fifth-grade words. Aim for 15 words, but keep all agreed actions, conditions and their order around the Trigger. Name known fields, people and limits. Start actions with verbs and name unclear actors. Do not invent details. A missing reply does not prove a failed write: check the result before retrying.

Under the table, add three items:

- **Constraint**: the case to decide first, and why.
- **The 80/20**: the cases its decision covers.
- **Open questions**: every Needs decision row, with its question, Owner and Default, or None. Use the named owner, or "feature owner" if none is given.

Open questions stay in the file. Print the table, the constraint and the 80/20 in the chat. Print nothing else.

## Notes

- Say what the product does, not what it should do.
- Before saving and printing, remove any em dashes or semicolons from the table and closing items.
