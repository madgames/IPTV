---
name: prompt-master
description: Restructure a messy brain-dump into a clear, complete task spec before executing it. Use when the user's request is long, rambling, contradictory, or mixes several asks — restructure first, confirm the reading, then run the task.
---

# Prompt-Master

When a request arrives as a messy brain-dump, do not start working on the first thing mentioned. Restructure it first.

## Process

1. **Parse the dump.** Pull out, in this order:
   - **Goal** — the actual outcome wanted (often buried mid-paragraph or stated last).
   - **Deliverables** — concrete artifacts to produce.
   - **Constraints** — deadlines, formats, tone, budget, tech choices, things explicitly ruled out.
   - **Context** — background facts that inform the work but aren't tasks.
   - **Open questions** — genuine ambiguities or contradictions in the dump.
2. **Resolve conflicts.** If two parts of the dump contradict, pick the later/more specific statement and note the choice. Only ask the user when the conflict genuinely changes the deliverable.
3. **Restate it.** Show a compact structured spec (Goal / Deliverables / Constraints / Assumptions). One short block, not a document.
4. **Execute immediately** against that spec unless an open question is blocking. Don't wait for approval of the restatement — it's there so the user can correct you mid-flight.

## Rules

- Never silently drop a requirement from the dump; if you deprioritize one, say so in Assumptions.
- Keep the user's own vocabulary in the spec so they can scan it fast.
- Multiple unrelated asks in one dump = numbered task list, tackled in order of dependency, not order mentioned.
