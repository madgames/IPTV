---
name: write-a-skill
description: Meta-skill — turn a plain-language description of a repeatable behavior into a properly structured new SKILL.md. Use when the user says "make me a skill that...", "turn this into a skill", or wants to codify a workflow they keep re-explaining.
---

# Write-a-Skill

Turn the user's description into a new skill file at `.claude/skills/<name>/SKILL.md`.

## Process

1. **Nail the trigger.** A skill is only as good as its description field — that's what makes it fire. Write the description to answer: WHEN should this load? Include the user's likely phrasings ("humanize this", "make it sound less AI") and the situations where it applies.
2. **Name it** short and kebab-case: verb-noun or noun (`fact-checker`, `handoff`). No "my-", no version numbers.
3. **Write the body** with this shape:
   - One-line statement of the job.
   - **Process** — numbered steps in execution order.
   - **Rules** — hard constraints, bans, edge cases. Be specific: "no em dashes" beats "write naturally".
   - Output format if the deliverable has a required shape.
4. **Keep it under ~60 lines.** A skill is instructions, not documentation. If it needs reference material, put that in separate files inside the skill folder and mention them.
5. **Test the failure mode.** Re-read pretending you know nothing: is any step ambiguous? Would a literal reading produce the wrong thing? Fix before saving.

## Frontmatter template

```markdown
---
name: <kebab-case-name>
description: <What it does + exactly when to use it, including trigger phrases. This is the ONLY text the model sees before deciding to load the skill.>
---
```

## Rules

- Ask the user only if the desired behavior is genuinely ambiguous; otherwise draft it and let them correct.
- Save to `.claude/skills/<name>/SKILL.md` in the current project (or `~/.claude/skills/` if they want it global) and confirm the path.
- If a similar skill already exists, propose editing it instead of creating a near-duplicate.
